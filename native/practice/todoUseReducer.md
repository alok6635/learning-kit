```
import { useEffect, useReducer } from 'react';
import { FlatList, StyleSheet, Text, TextInput, TouchableOpacity, View } from 'react-native';
import AsyncStorage from '@react-native-async-storage/async-storage';

const Todo = () => {
    const initialState = {
        inp: '',
        display: [],
        editIndex: null,
    };

    const reducer = (state, action) => {
        switch (action.type) {
            case 'INP':
                return { ...state, inp: action.payload };
            case 'ADD':
                if (state.editIndex !== null) {
                    const updated = state.display.map((item, index) =>
                        index === state.editIndex ? state.inp : item
                    );
                    return { ...state, display: updated, inp: '', editIndex: null };
                } else {
                    return { ...state, display: [...state.display, state.inp], inp: '' };
                }
            case 'DELETE':
                return {
                    ...state,
                    display: state.display.filter((_, i) => i !== action.payload),
                };
            case 'EDIT':
                return {
                    ...state,
                    inp: state.display[action.payload],
                    editIndex: action.payload,
                };
            case 'LOAD':
                return { ...state, display: action.payload };
            default:
                return state;
        }
    };

    const [state, dispatch] = useReducer(reducer, initialState);

    useEffect(() => {
        const getTodo = async () => {
            try {
                const saveTodo = await AsyncStorage.getItem('todo');
                if (saveTodo) {
                    dispatch({ type: 'LOAD', payload: JSON.parse(saveTodo) });
                }
            } catch (error) {
                console.log('Error fetching todo:', error);
            }
        };
        getTodo();
    }, []);

    useEffect(() => {
        const setTodo = async () => {
            try {
                await AsyncStorage.setItem('todo', JSON.stringify(state.display));
            } catch (error) {
                console.log('Error saving todo:', error);
            }
        };
        setTodo();
    }, [state.display]);

    return (
        <>
            <View style={styles.container}>
                <TextInput style={styles.input} placeholder="Enter Input" value={state.inp} onChangeText={(value) => dispatch({ type: 'INP', payload: value })} />
                <TouchableOpacity onPress={() => dispatch({ type: 'ADD' })}>
                    <Text style={styles.btn}>{state.editIndex !== null ? 'Update' : 'Add'}</Text>
                </TouchableOpacity>
            </View>
            <FlatList data={state.display} keyExtractor={(item, index) => index.toString()}
                renderItem={({ item, index }) => (
                    <View style={styles.displayContainer}>
                        <Text>{item}</Text>
                        <View style={styles.btnCover}>
                            <TouchableOpacity onPress={() => dispatch({ type: 'EDIT', payload: index })}>
                                <Text style={styles.btn}>Edit</Text>
                            </TouchableOpacity>
                            <TouchableOpacity onPress={() => dispatch({ type: 'DELETE', payload: index })}>
                                <Text style={styles.btn}>Delete</Text>
                            </TouchableOpacity>
                        </View>
                    </View>
                )}
            />
        </>
    );
};
export default Todo;

const styles = StyleSheet.create({
    container: {
        padding: 10,
        marginTop: 20,
        flexDirection: 'row',
        justifyContent: 'space-between',
        alignItems: 'center',
        elevation: 4,
        backgroundColor: '#fff',
        margin: 15,
        borderRadius: 5,
    },
    input: {
        width: '80%',
        borderWidth: 1,
        borderColor: 'black',
        borderRadius: 5,
        paddingLeft: 10,
        paddingVertical: 8,
    },
    btn: {
        backgroundColor: '#000',
        color: '#fff',
        padding: 10,
        borderRadius: 5,
        marginLeft: 5,
    },
    btnCover: {
        flexDirection: 'row',
    },
    displayContainer: {
        flexDirection: 'row',
        justifyContent: 'space-between',
        alignItems: 'center',
        padding: 5,
        borderRadius: 8,
        marginBottom: 10,
        elevation: 7,
        backgroundColor: '#fff',
        marginLeft: 10,
        marginRight: 10,
    },
});

```

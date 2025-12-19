```
import { FlatList, StyleSheet, Text, TextInput, TouchableOpacity, View } from 'react-native';
import UseTodo from './UseTodo';
const Todo = () => {
    const { handleAdd, handleDel, handleEdit,editIndex,display,inp,setInp } = UseTodo();
    return (
        <>
            <View style={styles.container}>
                <TextInput style={styles.input} placeholder='Enter Input' value={inp} onChangeText={setInp} />
                <TouchableOpacity onPress={handleAdd}>
                    <Text style={styles.btn}>{editIndex !== null ? "Update" : "Add"}</Text>
                </TouchableOpacity>
            </View>

            <FlatList
                data={display}
                keyExtractor={(item, index) => index.toString()}
                renderItem={({ item, index }) => (
                    <View style={styles.displayContainer}>
                        <Text>{item}</Text>
                        <View style={styles.btnCover}>
                            <TouchableOpacity onPress={() => handleEdit(index)}>
                                <Text style={styles.btn}>Edit</Text>
                            </TouchableOpacity>
                            <TouchableOpacity onPress={() => handleDel(index)}>
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
        justifyContent: "space-between",
        alignItems: 'center',
        elevation: 4,
        backgroundColor: '#fff',
        margin: 15,
        borderRadius: 5
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
        marginRight: 10
    },
});

#UseTodo.js-
import { useEffect, useState } from "react";
import AsyncStorage from '@react-native-async-storage/async-storage';

const UseTodo = () => {
    const [inp, setInp] = useState('');
    const [display, setDisplay] = useState([]);
    const [editIndex, setEditIndex] = useState(null);

    const handleAdd = () => {
        if (editIndex !== null) {
            const updatedDisplay = display.map((item, index) =>
                index === editIndex ? inp : item
            );
            setDisplay(updatedDisplay);
            setEditIndex(null);
        } else {
            setDisplay([...display, inp]);
        }
        setInp('');
    };
    const handleDel = (index) => {
        const updated = display.filter((_, id) => id !== index);
        setDisplay(updated);
    };
    const handleEdit = (index) => {
        setEditIndex(index);
        setInp(display[index]);
    };
    // Get AsyncStorage Data
    useEffect(() => {
        const getTodo = async () => {
            try {
                const saveTodo = await AsyncStorage.getItem('todo');
                if (saveTodo) {
                    setDisplay(JSON.parse(saveTodo));
                }
            } catch (error) {
                console.log('Error fetching todo:', error);
            }
        };
        getTodo();
    }, []);
    // Set AsyncStorage Data when "display" changes
    useEffect(() => {
        const setTodo = async () => {
            try {
                await AsyncStorage.setItem("todo", JSON.stringify(display));
            } catch (error) {
                console.log('Error saving todo:', error);
            }
        };
        setTodo();
    }, [display]);
    return { handleAdd, handleDel, handleEdit, editIndex, display, inp, setInp }
}
export default UseTodo

```

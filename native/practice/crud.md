```
import React, { useEffect, useState } from "react";
import { View, Text, TextInput, StyleSheet, TouchableOpacity, FlatList } from "react-native";
import axios from "axios";

const Crud = () => {
    const [cred, setCred] = useState({ id: "", name: "", number: "" });
    const [display, setDisplay] = useState([]);
    const [error, setError] = useState(null);
    const [editIndex, setEditIndex] = useState(false)
    const baseUrl = "http://192.168.1.3:3000/list";
    //Create-
    const handleAdd = async () => {
        try {
            const response = await axios.post(baseUrl, cred);
            setDisplay([...display, response.data]);
            setCred({ id: "", name: "", number: "" })
        } catch (error) {
            setError(error);
        }
    }
    // Read-
    const getData = async () => {
        try {
            const response = await axios.get(baseUrl);
            setDisplay(response.data);
        } catch (error) {
            setError(error)
        }
    }

    useEffect(() => {
        getData();
    }, [])
    // Delete-
    const handleDel = async (id) => {
        await axios.delete(`${baseUrl}/${id}`);
        const filterData = display.filter((item) => item.id !== id);
        setDisplay(filterData);
    }
    //Update-
    const handleEdit = async (item) => {
        setCred(item);
         setEditIndex(true); 
    }
const handleUpdate = async()=>{
     try {
        await axios.put(`${baseUrl}/${cred.id}`,cred);
        const updatedData = display.map((item)=> item.id === cred.id ? cred :item);
        setDisplay(updatedData);
        setCred({ id: "", name: "", number: "" });
        setEditIndex(false);   
     } catch (error) {
        setError(error)
     }
}
    return (
        <View style={styles.container}>
            {error && <Text style={{ color: "red" }}>{error}</Text>}
            <View style={styles.form}>
                <TextInput style={styles.input} placeholder="Enter ID" value={cred.id} onChangeText={(value) => setCred({ ...cred, id: value })} />
                <TextInput style={styles.input} placeholder="Enter name" value={cred.name} onChangeText={(value) => setCred({ ...cred, name: value })} />
                <TextInput style={styles.input} placeholder="Enter number" value={cred.number} onChangeText={(value) => setCred({ ...cred, number: value })} />
                {
                    editIndex ? (<TouchableOpacity style={styles.btn} onPress={handleUpdate}>
                        <Text style={styles.btnText}>Update</Text>
                    </TouchableOpacity>) :
                        <TouchableOpacity style={styles.btn} onPress={handleAdd}>
                            <Text style={styles.btnText}>Add</Text>
                        </TouchableOpacity>
                }
            </View>
            <View style={[styles.row, styles.header]}>
                <Text style={styles.cell}>ID</Text>
                <Text style={styles.cell}>Name</Text>
                <Text style={styles.cell}>Number</Text>
                <Text style={styles.cell}>Actions</Text>
            </View>

            <FlatList
                data={display}
                keyExtractor={(item) => item.id.toString()}
                renderItem={({ item }) => (
                    <View style={styles.row}>
                        <Text style={styles.cell}>{item.id}</Text>
                        <Text style={styles.cell}>{item.name}</Text>
                        <Text style={styles.cell}>{item.number}</Text>
                        <View style={styles.actions}>

                            <TouchableOpacity style={styles.btn} onPress={() => handleEdit(item)}>
                                <Text style={styles.btnText}>Edit</Text>
                            </TouchableOpacity>
                            <TouchableOpacity style={styles.btn} onPress={() => handleDel(item.id)}>
                                <Text style={styles.btnText}>Delete</Text>
                            </TouchableOpacity>
                        </View>
                    </View>
                )}
            />
        </View>
    );
};
const styles = StyleSheet.create({
    container: { padding: 20 },
    form: { marginBottom: 20 },
    input: {
        borderWidth: 1,
        borderColor: "#ccc",
        padding: 8,
        marginBottom: 10,
        borderRadius: 5,
    },
    btn: {
        backgroundColor: "black",
        borderRadius: 5,
        padding: 6,
        margin: 2,
    },
    btnText: {
        fontSize: 16,
        color: "#fff",
        textAlign: "center"
    },
    row: {
        flexDirection: "row",
        borderBottomWidth: 1,
        borderColor: "#ddd",
        paddingVertical: 10,
        alignItems: "center",
    },
    header: {
        backgroundColor: "#f2f2f2"
    },
    cell: {
        textAlign: "center",
        flex: 1
    },
    actions: {
        flex: 1,
        flexDirection: "row",
        justifyContent: "space-around"
    },
});
export default Crud;

#db.json-
{
  "list": [
    {
      "id": "123",
      "name": "ccff",
      "number": "5678797809"
    }
  ]
}
```

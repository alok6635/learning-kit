**# get api**

```
import { ActivityIndicator, FlatList, StyleSheet, Text, TouchableOpacity, View } from 'react-native'
import React, { useState } from 'react'
import axios from 'axios'

const Temp = () => {
    const [loading, setLoading] = useState(false);
    const [error, setError] = useState();
    const [display, setDisplay] = useState([]);
    const baseUrl = "https://fakestoreapi.com/product";

//# axios- using async await with (try & catch)-
     const handleApi = async() => {
        setLoading(true);
        try {
            const response = await axios.get(baseUrl);
            setDisplay(response.data)
        } catch (error) {
            setError(error.message);
        }
        finally {
            setLoading(false);
        }
    }

//# fetch- using .then & .catch-
    // const handleApi = () => {
    //     setLoading(true);
    //     axios.get(baseUrl)
    //         .then((res) => setDisplay(res.data))
    //         .catch((err) => setError(err.message))
    //         .finally(() => setLoading(false));
    // };

//# fetch -using async await with (try & catch)-
// const handleApi = async () => {
//   setLoading(true);
//   setError(null);
//   try {
//     const res = await fetch(baseUrl);
//     if (!res.ok) {
//       throw new Error(`HTTP error! Status: ${res.status}`);
//     }
//     const data = await res.json();
//     setDisplay(data);
//   } catch (err) {
//     console.log("gfchvjb",err)
//     setError(err.message);
//   } finally {
//     setLoading(false);
//   }
// }

//# fetch- using .then & .catch-
// const handleApi = () => {
//   setLoading(true);
//   setError(null);
//   fetch(baseUrl).then((res) => {
//       if (!res.ok) {
//         throw new Error(`HTTP error! Status: ${res.status}`);
//       }
//       return res.json();
//     })
//     .then((data) => {
//       setDisplay(data);
//     })
//     .catch((err) => {
//       setError(err.message);
//     })
//     .finally(() => {
//       setLoading(false);
//     });
// };

// ##Note- Axios 404 ko directly error banata hai, isliye "Request failed with status code 404" milta hai.Fetch by default 404 ko error nahi manta.
// Agar URL galat hai (404 aaya), tab bhi fetch resolve ho jata hai aur res.ok === false hota hai.
// Tumne await res.json() likha hai, lekin server ne 404 ke case mein HTML error page bheja hoga

    return (
        <>
            <View style={styles.container}>
                <TouchableOpacity style={styles.button} onPress={handleApi}>
                    <Text style={styles.buttonText}>Api call</Text>
                </TouchableOpacity>
                {loading && <ActivityIndicator size="large" color="blue" />}
                {error && <Text style={styles.error}>{error}</Text>}
                <FlatList
                    data={display}
                    keyExtractor={(item) => item.id.toString()}
                    renderItem={({ item }) => (
                        <View style={styles.itemBox}>
                            <Text style={styles.itemText}>{item.title}</Text>
                        </View>
                    )}
                />
            </View>
        </>
    )
}
export default Temp;

const styles = StyleSheet.create({
    container: {
        flex: 1,
        padding: 16
    },
    button: {
        width: 100,
        backgroundColor: "blue",
        padding: 12,
        borderRadius: 8,
        alignItems: "center",
        marginBottom: 10,
    },
    buttonText: { color: "white", fontSize: 16, fontWeight: "bold" },
    error: { color: "red", marginVertical: 10 },
    itemBox: { padding: 10, borderBottomWidth: 1, borderBottomColor: "#ccc" },
    itemText: { fontSize: 14 },
});
```

## post Api-

```
import { Alert, StyleSheet, Text, TextInput, TouchableOpacity, View } from 'react-native'
import React, { useState } from 'react'
import axios from 'axios'

const Temp = () => {
    const [error, setError] = useState();
    const baseUrl = "https://jsonplaceholder.typicode.com/albums";
    const [cred, setCred] = useState({ name: '', pass: '' })

//#Using axios-  try & catch, async & await- 
  const handleApi = async () => {
    try {
      const response = await axios.post(baseUrl, {
        headers: {
          "Content-Type": "application/json",
        },
      }, cred
      )
      if (response.status === 201) {
        Alert.alert("post created")
      }
    } catch (error) {
      setError(error.message)
    }
  }
  

//#Using axios- .then & .catch- 

    // const handleApi = () => {
    //   setError(null);
    //   axios.post(baseUrl, cred, {
    //       headers: {
    //         "Content-Type": "application/json",
    //       },
    //     })
    //     .then((res) => {
    //       if (res.status === 201) {
    //         Alert.alert("Success", "Post created");
    //       } else {
    //         Alert.alert("Error", `Unexpected status: ${res.status}`);
    //       }
    //     })
    //     .catch((error) => {
    //       console.log("Error in POST:", error);
    //       setError(error.message);
    //       Alert.alert("Error", error.message);
    //     });
    // };

//#Using fetch-  try & catch async &n await- 

    // const handleApi = async () => {
    //   try {
    //     const res = await fetch(baseUrl, {
    //       method: "POST",
    //       headers: {
    //         "Content-Type": "application/json"
    //       },
    //       body: JSON.stringify(cred)
    //     });
    //     if (res.status === 201) {
    //       Alert.alert("Post created");
    //     } else {
    //       throw new Error(`HTTP error! Status: ${res.status}`);
    //     }
    //   } catch (error) {
    //     setError(error.message);
    //   }
    // };

//#Using fetch- .then & .catch- 

    // const handleApi = () => {
    //     setError(null);
    //     fetch(baseUrl, {
    //         method: "POST",
    //         headers: {
    //             "Content-Type": "application/json"
    //         },
    //         body: JSON.stringify(cred)
    //     })
    //         .then((res) => {
    //             if (!res.ok) {
    //                 throw new Error(`HTTP error! Status: ${res.status}`);
    //             }
    //             return res.json();
    //         })
    //         .then((data) => {
    //             Alert.alert("Post created");
    //             console.log("Response Data:", data);
    //         })
    //         .catch((error) => {
    //             setError(error.message);
    //             Alert.alert("Error", error.message);
    //         });
    // };
    return (
        <>
            <View style={styles.container}>
                <TextInput style={styles.input} placeholder='name' value={cred.name} onChangeText={(value) => setCred({ ...cred, name: value })} />
                <TextInput style={styles.input} placeholder='pass' value={cred.pass} onChangeText={(value) => setCred({ ...cred, pass: value })} />
                <TouchableOpacity style={styles.button} onPress={handleApi}>
                    <Text style={styles.buttonText}>Add</Text>
                </TouchableOpacity>
                {error && <Text style={styles.error}>{error}</Text>}
            </View>
        </>
    )
}
export default Temp;
const styles = StyleSheet.create({
    container: {
        flex: 1,
        padding: 16
    },
    button: {
        backgroundColor: "blue",
        padding: 12,
        borderRadius: 8,
        alignItems: "center",
        marginBottom: 10,
    },
    buttonText: { color: "white", fontSize: 16 },
    error: { color: "red", marginVertical: 10 },
    itemBox: { padding: 10, borderBottomWidth: 1, borderBottomColor: "#ccc" },
    itemText: { fontSize: 14 },
    input: {
        width: 375,
        height: 39,
        borderWidth: 1,
        borderColor: '#000',
        borderRadius: 5,
        marginBottom: 10,
        padding: 4
    }
});
```


### other api call-
```
**# Api call**

```
import { ActivityIndicator, FlatList, StyleSheet, Text, TouchableOpacity, View } from 'react-native';
import React, { useState } from 'react';
import axios from 'axios';


const ApiCall = () => {
    const [product, setProduct] = useState([]);
    const [err, setErr] = useState(null);
    const [loading, setLoading] = useState(false);

    const getData = async () => {
        setErr(null); 
        setLoading(true); 
        try {
            const response = await axios.get('https://fakestoreapi.com/products');
            setProduct(response.data);
        } catch (error) {
            setErr(error.message);
        } finally {
            setLoading(false); 
        }
    };

    return (
        <View style={styles.container}>
            <TouchableOpacity style={styles.btn} onPress={getData}>
                <Text style={styles.text}>Get Data</Text>
            </TouchableOpacity>
            {
               loading ? (
            <ActivityIndicator size="large" color="blue"/>
        ): err ? (
            <Text style={styles.error}>{err}</Text>
            ) :(
                <FlatList
                data={product}
                keyExtractor={(item) => item.id.toString()}
                renderItem={({ item }) => (
                    <View style={styles.display}>
                        <Text>{item.title}</Text>
                    </View>
                )}
            />
            )
            }
        </View>
    );
};
export default ApiCall;

const styles = StyleSheet.create({
    container: {
        marginTop: 30,
        paddingHorizontal: 10,
        margin:'auto'
    },
    btn: {
        width:100,
        justifyContent: 'center',
        alignItems: 'center',
        padding: 10,
        backgroundColor: '#4CAF50',
        borderColor: 'black',
        borderWidth: 1,
        borderRadius: 5,
        marginBottom:30

    },
    text: {
        color: '#fff',
        fontSize: 16
    },
    display: {
        borderRadius: 5,
        borderWidth: 1,
        borderColor: "black",
        padding: 5,
        margin: 5
    },
    error: {
        color: 'red',
        textAlign: 'center',
        marginTop: 10
    }
});

```

```

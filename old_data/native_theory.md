
**# stack navigation**

```
## App.jsx-

import React from 'react';
import { createStackNavigator } from '@react-navigation/stack';
import { NavigationContainer } from '@react-navigation/native';
import Login from './screens/Login';
import Register from './screens/Register';
const Stack = createStackNavigator();

const App = () => {
  return (
    <NavigationContainer>
      <Stack.Navigator screenOptions={{ headerTitleAlign: 'center' }}>
        <Stack.Screen name="Login" component={Login} options={{ title: 'Login Screen',headerShown:false}} />
        <Stack.Screen name="Register" component={Register} options={{ title: 'Register Screen',headerShown:false }} />
      </Stack.Navigator>
    </NavigationContainer>
  );
};
export default App;

## Login.jsx-
import React from 'react';
import { StyleSheet, Text, View, TouchableOpacity, Button } from 'react-native';
import { useNavigation } from '@react-navigation/native';

const Login = () => {
  const navigation = useNavigation();
  return (
    <View style={styles.container}>
      <Text style={styles.title}>Welcome to Login</Text>
      <TouchableOpacity 
        onPress={() => navigation.navigate("Register", { email: 'alokyadav6635@gmail.com' })} 
        style={styles.button}
      >
        <Text style={styles.text}>Go to Register Screen</Text>
      </TouchableOpacity>
    </View>
  );
};
export default Login;
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#F8F9FA',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
    color: '#333',
  },
  button: {
    padding: 15,
    backgroundColor: '#007BFF',
    borderRadius: 8,
    marginVertical: 10,
    shadowColor: '#000',
    shadowOffset: { width: 0, height: 4 },
    shadowOpacity: 0.3,
    shadowRadius: 5,
    elevation: 5,
  },
  text: {
    color: '#fff',
    fontSize: 18,
    fontWeight: 'bold',
  },
});

## Register.jsx-
import React from 'react';
import { StyleSheet, Text, View, TouchableOpacity, Button } from 'react-native';
import { useNavigation, useRoute } from '@react-navigation/native';

const Register = () => {
    const navigation = useNavigation();
    const route = useRoute();
    return (
        <View style={styles.container}>
            <Text style={styles.title}>Register Here</Text>
            <TouchableOpacity
                onPress={() => navigation.navigate("Login")}
                style={styles.button}
            >
                <Text style={styles.text}>Go to Login Screen</Text>
            </TouchableOpacity>
            <Text style={styles.emailText}>{route.params?.email || "No email passed"}</Text>
            <Button title='Go back' onPress={() => navigation.goBack()} color="#DC3545" />
        </View>
    );
};
export default Register;
const styles = StyleSheet.create({
    container: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
        backgroundColor: '#F8F9FA',
    },
    title: {
        fontSize: 24,
        fontWeight: 'bold',
        marginBottom: 20,
        color: '#333',
    },
    button: {
        padding: 15,
        backgroundColor: '#28A745',
        borderRadius: 8,
        marginVertical: 10,
        shadowColor: '#000',
        shadowOffset: { width: 0, height: 4 },
        shadowOpacity: 0.3,
        shadowRadius: 5,
        elevation: 5,
    },
    text: {
        color: '#fff',
        fontSize: 18,
        fontWeight: 'bold',
    },
    emailText: {
        fontSize: 16,
        marginVertical: 10,
        color: '#333',
        fontStyle: 'italic',
    },
});
```


**# drawer navigator important command**

```
step-I 
npm install @react-navigation/drawer

step-II
## need to install and configure the libraries that are required by the drawer navigator-
npm install react-native-gesture-handler react-native-reanimated

step-III
npm install react-native-reanimated

step-IV
## Add Reanimated's babel plugin-
babel.config.js file-
  module.exports = {
    presets: [
    ],
    plugins: [
      'react-native-reanimated/plugin',
    ],
  }; 
```

**# normal Drawer**

```
## DrawerNavigator-

import { Image, StyleSheet, Text } from 'react-native';
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import Home from './screens/Home';
import Chat from './screens/Chat';
import Settings from './screens/Settings';
import HelpSupport from './screens/HelpSupport';
const Drawer = createDrawerNavigator();

const App = () => {
    return (
        <NavigationContainer>
            <Drawer.Navigator
                screenOptions={{
                drawerActiveBackgroundColor: 'pink',
                drawerStyle: { backgroundColor: 'cyan' },
                drawerActiveTintColor: 'red',
                drawerInactiveTintColor: 'white',
            }}
            >
                <Drawer.Screen name="Home" component={Home}
                    options={{
                        drawerIcon: ({ size, focused }) => (
                            <Image style={{
                                width: size, height: size, tintColor: focused ? 'white' : 'white',
                            }} source={require('../../img/home.png')} />
                        ),
                        drawerLabel: ({ size, color }) => (
                            <Text style={{ color: color, fontSize: 18 }}>
                                Home
                            </Text>
                        ),
                    }}
                />
                <Drawer.Screen name="Chat" component={Chat}
                    options={{
                        drawerIcon: ({ size, focused }) => (
                            <Image style={{
                                width: size, height: size, tintColor: focused ? 'blue' : 'white',
                            }} source={require('../../img/chat.png')} />
                        ),
                        drawerLabel: ({ size, color }) => (
                            <Text style={{ color: color, fontSize: 18 }}>
                                Chat
                            </Text>
                        ),
                    }}
                />
                <Drawer.Screen name="Settings" component={Settings}
                    options={{
                        drawerIcon: ({ size, focused }) => (
                            <Image style={{
                                width: size, height: size, tintColor: focused ? 'blue' : 'white',
                            }} source={require('../../img/setting.png')} />
                        ),
                        drawerLabel: ({ size, color }) => (
                            <Text style={{ color: color, fontSize: 18 }}>
                                Settings
                            </Text>
                        ),
                    }}
                />
                <Drawer.Screen name="HelpSupport" component={HelpSupport}
                    options={{
                        drawerIcon: ({ size, focused }) => (
                            <Image style={{
                                width: size, height: size, tintColor: focused ? 'blue' : 'white',
                            }} source={require('../../img/help.png')} />
                        ),
                        drawerLabel: ({ size, color }) => (
                            <Text style={{ color: color, fontSize: 18 }}>
                                HelpSupport
                            </Text>
                        ),
                    }}
                />
            </Drawer.Navigator>
        </NavigationContainer>
    );
};
export default App;
const styles = StyleSheet.create({
    icon: {
        width: 30,
        height: 30,
    },
});
```

**# custom Drawer**

```
## App.jsx-

import { Image, StyleSheet, Text } from 'react-native';
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createDrawerNavigator } from '@react-navigation/drawer';
import Home from './screens/Home';
import Chat from './screens/Chat';
import Settings from './screens/Settings';
import HelpSupport from './screens/HelpSupport';
import CustomDrawer from './CustomDrawer';
const Drawer = createDrawerNavigator();

const App = () => {
    return (
        <NavigationContainer>
            <Drawer.Navigator
                drawerContent={(props) => <CustomDrawer {...props} />}>
                <Drawer.Screen name="Home" component={Home}/>
                <Drawer.Screen name="Chat" component={Chat}/>
                <Drawer.Screen name="Settings" component={Settings}/>
                <Drawer.Screen name="HelpSupport" component={HelpSupport}/>
            </Drawer.Navigator>
        </NavigationContainer>
    );
};
export default App;
const styles = StyleSheet.create({
    icon: {
        width: 30,
        height: 30,
    },
});

##CustomDrawer -

import { Image, StyleSheet, Text, TouchableOpacity } from 'react-native';
import React from 'react';
import { SafeAreaView } from 'react-native-safe-area-context';

const CustomDrawer = ({navigation}) => {
    return (
        <SafeAreaView style={{ flex: 1, backgroundColor: 'white' }}>
            <Image source={require("../../img/user.png")} style={styles.img} />
            <Text style={styles.text}>{"View Profile"}</Text>
            <TouchableOpacity style={styles.btn} onPress={()=>navigation.navigate("Home")}>
                <Image source={require("../../img/home.png")} style={styles.menuImg}/>
                <Text style={styles.text}>Home</Text>
            </TouchableOpacity>
            <TouchableOpacity style={styles.btn} onPress={()=>navigation.navigate("Chat")}>
                <Image source={require("../../img/chat.png")} style={styles.menuImg}/>
                <Text style={styles.text}>Chat</Text>
            </TouchableOpacity>
            <TouchableOpacity style={styles.btn} onPress={()=>navigation.navigate("Settings")}>
                <Image source={require("../../img/setting.png")} style={styles.menuImg}/>
                <Text style={styles.text}>Setting</Text>
            </TouchableOpacity>
            <TouchableOpacity style={styles.btn} onPress={()=>navigation.navigate("HelpSupport")}>
                <Image source={require("../../img/help.png")} style={styles.menuImg}/>
                <Text style={styles.text}>HelpSupport</Text>
            </TouchableOpacity>
        </SafeAreaView>
    )
}
export default CustomDrawer;
const styles = StyleSheet.create({
    img: {
        width: 100,
        height: 100,
        alignSelf: 'center'
    },
    text: {
        textAlign: 'center',
        marginLeft:5
    },
    btn: {
        flexDirection: 'row',
        width: '100',
        height: 50,
        alignItems:'center'

    },
    menuImg: {
        width: 20,
        height: 20,
        marginLeft:20,
    }
})
```

**# custom bottom Navigation**

```
##App.jsx-

import { Image, ImageBackground, StyleSheet, Text, View } from 'react-native';
import React from 'react';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import Home from './tabs/Home';
import Search from './tabs/Search';
import AddPost from './tabs/AddPost';
import Favorite from './tabs/Favorite';
import CustomBottomTab from './CustomBottomTab';
const Bottom = createBottomTabNavigator();

const App = () => {
    return (
        <Bottom.Navigator
        tabBar={(props)=> <CustomBottomTab {...props}/>}>
            <Bottom.Screen name="Home" component={Home} options={{headerShown:false}}/>
            <Bottom.Screen name="search" component={Search} options={{headerShown:false}}/>
            <Bottom.Screen name="AddPost" component={AddPost} options={{headerShown:false}}/>
            <Bottom.Screen name="Favorite" component={Favorite} options={{headerShown:false}}/>
        </Bottom.Navigator>
    )
}
export default App;
const styles = StyleSheet.create({})

##CustomBottomTab-

import { Image, StyleSheet, Text, TouchableOpacity, View } from 'react-native';
import React from 'react';

const CustomBottomTab = ({ state, descriptors, navigation }) => {
  return (
    <View style={styles.container}>
      {state.routes.map((item, index) => {
        const isFocused = state.index === index;
        const color = isFocused ? 'red' : 'green';

        return (
          <TouchableOpacity
            key={index}
            style={styles.main}
            onPress={() => navigation.navigate(item.name)}>
            <Image
              source={
                item.name === "Home"
                  ? require("../../img/home.png")
                  : item.name === "search"
                  ? require("../../img/search.png")
                  : item.name === "AddPost"
                  ? require("../../img/post.png")
                  : item.name === "Favorite"
                  ? require("../../img/fav.png")
                  : null
              }
              style={[styles.img, { tintColor: color }]}
            />
            <Text style={{ color }}>{item.name}</Text>
          </TouchableOpacity>
        );
      })}
    </View>
  );
};
export default CustomBottomTab;

const styles = StyleSheet.create({
  container: {
    flexDirection: 'row',
    width: '100%',
    height: 50,
    justifyContent: 'space-evenly',
    alignItems: 'center',
    backgroundColor: 'white',
    paddingTop: 3,
  },
  img: {
    width: 20,
    height: 20,
  },
  main: {
    alignItems: 'center',
    gap: 5,
  },
});

```

**# Normal bottom navigation**

```
import { Image, ImageBackground, StyleSheet, Text, View } from 'react-native';
import React from 'react';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import Home from './tabs/Home';
import Search from './tabs/Search';
import AddPost from './tabs/AddPost';
import Favorite from './tabs/Favorite';
const Bottom = createBottomTabNavigator();

const App = () => {
    return (
        <Bottom.Navigator screenOptions={{
            tabBarStyle:{
             height:60
        },
        tabBarActiveTintColor:'red',
        tabBarInactiveTintColor:'green'
        }}>
            <Bottom.Screen name="Home" component={Home}
                options={{
                    headerShown: false, tabBarIcon: ({ size, color }) => {
                        return <Image source={require("../../img/home.png")} style={{ width: size, height: size, tintColor: color }} />
                    }
                }} />
            <Bottom.Screen name="search" component={Search}
                options={{
                    headerShown: false, tabBarIcon: ({ size, color }) => {
                        return <Image source={require("../../img/search.png")} style={{ width: size, height: size, tintColor: color }} />
                    }
                }} />
            <Bottom.Screen name="AddPost" component={AddPost}
                options={{
                    headerShown: false, tabBarIcon: ({ size, color }) => {
                        return <Image source={require("../../img/post.png")} style={{ width: size, height: size, tintColor: color }} />
                    }
                }} />
            <Bottom.Screen name="Favorite" component={Favorite}
                options={{
                    headerShown: false, tabBarIcon: ({ size, color }) => {
                        return <Image source={require("../../img/fav.png")} style={{ width: size, height: size, tintColor: color }} />
                    }
                }} />
        </Bottom.Navigator>
    )
}
export default App;
```


**# create apk file in macbbook**


https://www.youtube.com/watch?v=l3CZmXtEe_Y

```
fallow steps-
https://archive.reactnative.dev/docs/signed-apk-android

step-I 
keytool -genkeypair -v -keystore my-upload-key.keystore -alias my-key-alias -keyalg RSA -keysize 2048 -validity 10000

step-II
* change the file gradle.properties-
MYAPP_UPLOAD_STORE_FILE=my-upload-key.keystore
MYAPP_UPLOAD_KEY_ALIAS=my-key-alias
MYAPP_UPLOAD_STORE_PASSWORD=123456
MYAPP_UPLOAD_KEY_PASSWORD=123456

step-III
android > app> build.gradle
set the below code-

signingConfigs {
        release {
            if (project.hasProperty('MYAPP_UPLOAD_STORE_FILE')) {
                storeFile file(MYAPP_UPLOAD_STORE_FILE)
                storePassword MYAPP_UPLOAD_STORE_PASSWORD
                keyAlias MYAPP_UPLOAD_KEY_ALIAS
                keyPassword MYAPP_UPLOAD_KEY_PASSWORD
            }
        }
    }

    buildTypes {
        debug {
            signingConfig signingConfigs.debug
        }
        release {
            // Caution! In production, you need to generate your own keystore file.
            // see https://reactnative.dev/docs/signed-apk-android.
            signingConfig signingConfigs.debug
            minifyEnabled enableProguardInReleaseBuilds
            proguardFiles getDefaultProguardFile("proguard-android.txt"), "proguard-rules.pro"
            signingConfig signingConfigs.release
        }
    }

step-IV
move the-  my-upload-key.keystore file in the android > app 

step-V run next command
cd android
 ./gradlew assembleRelease

step-VI

check output - android > app > build > outputs > apk > release > app.release.apk

```

<details>
 <Summary> Environment setup</Summary>



**# react native cli**
* step I- installing Node via Chocolatey,a popular package manager for Windows.
           open windows powercell(run as a administrative). & run below command.
```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol 
      = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object 
    System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
 * Step II- react native requires Java SDE Development Kit(JDK).
```  
choco install -y nodejs-lts microsoft-openjdk17
```
* check versions-
choco- choco -v
java- java --version

* step III- install andriod studio
```
* Android SDK Platform 34
   Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image
   Next, select the "SDK Tools" tab and check the box next to "Show Package Details" here as well.Look for and expand the Android SDK 
   Build-Tools entry, then make sure that 34.0.0 is selected.Finally, click "Apply" to download and install the Android SDK and related 
   build tools.
* download SDK & emulator
* configure the ANDROID_HOME environment variable.
```
* step-IV
* create new poject- npx react-native init projectName
* run project- npm start


   
**# react native setup of  windows**

**# expo**
 * require only node 
 * check version:- node -v
```
open cmd-
* required- node,andriod studio
   * install andriod studio-
I- create a folder and runcommand:- npx create-expo-app projectName
II- cd AwesomeProject
III- code .(open in vs code)
IV- npx expo start
``` 

</details>

**# vector icons**

npm i react-native-vector-icons
https://oblador.github.io/react-native-vector-icons/

android/app/build.gradle
apply from: file("../../node_modules/react-native-vector-icons/fonts.gradle");
  
**# insert splash screen**

https://www.youtube.com/watch?v=7zjJXJjF-pM


  **# change app icons**
  * https://easyappicon.com/ inert here icon and find zip file.
  * then replace our folder- andriod-app-src-main-res- replace here
  * npx react-native run android

</details>

```



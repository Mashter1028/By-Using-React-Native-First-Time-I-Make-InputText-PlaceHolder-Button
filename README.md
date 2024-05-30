# By-Using-React-Native-First-Time-I-Make-InputText-PlaceHolder-Button

import { StyleSheet, Text, View,TextInput, Button} from 'react-native'
import React, { useState } from 'react'
import { Colors } from 'react-native/Libraries/NewAppScreen';

export default function App() {
  const [name ,setName] = useState('');
  const [password , setPassword] = useState('');
  const [Email , setEmail] = useState('');
  const [display ,setDisplay] = useState(false)

  const resetdetails = ()=>{
    setDisplay:(false);
setEmail('');
setPassword('');
setName('');
  }

  return (
    <View style={{flex:1}}>
      <Text>Name:</Text>
      <TextInput 
      style={styles.allpcholder}
      placeholder='Enter Your Name'
      onChangeText={(text)=>setName(text)}
      value={name}
      />


      <Text>Password:</Text>
      <TextInput 
      style={styles.allpcholder}
      placeholder='Enter Your Password'
      secureTextEntry={true}
      onChangeText={(text)=>setPassword(text)}
      value={password}
      />


      <Text>Email:</Text>
      <TextInput 
      style={styles.allpcholder}
      placeholder='Enter Your Email'
      onChangeText={(text)=>setEmail(text)}
      value={Email}
      />

      <View style={{margin:20,}}>
      <Button title='Print Details'onPress={()=>setDisplay(true)} />
      </View>

      <View style={{marginLeft:20,marginRight:20,}}>
      <Button color={'red'} title='Clear Details'onPress={resetdetails} />
     
      {
        display?
        <View>
         <Text style={{fontSize:20,}}>User Name Is {name}</Text>
         <Text style={{fontSize:20,}}>User Password Is Hidder</Text>
         <Text style={{fontSize:20,}}>User Email Is {Email}</Text>
        </View>
        : null
      }
       </View>
    </View>
  )
}



const styles = StyleSheet.create({
allpcholder:{
  backgroundColor:'gray',
  borderRadius:9,
  borderColor:'lightgray',
  borderWidth:1,
  marginLeft:10,
  marginRight:20,
}

})

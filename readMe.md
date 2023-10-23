## UseReducer ile Rastgele kutu uygulması 



#### Random rgb box oluşturma  
import { useState } from 'react';
import { StyleSheet, View ,Button, FlatList} from 'react-native';

export default function App() {
  const [colors, setColors] = useState([]);

  const randomColor = () => {
    const red = Math.floor(Math.random() * 256);
    const green = Math.floor(Math.random() * 256);
    const blue = Math.floor(Math.random() * 256);
    return `rgb(${red},${green},${blue})`;
  };
  return (
    <View  style={{marginVertical: 50 }}>
      <Button
       
        title="Kutu Ekle"
        onPress={() => {
          setColors([...colors, randomColor()]);
        }}
      />
      <FlatList
        data={colors}
        renderItem={({ item }) => {
          return (
            <View
              style={{
                height: 150,
                width: 150,
                backgroundColor: item,
                marginVertical: 20,
              }}
            />
          );
        }}
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
  marginVertical : 50 ,
  },
});

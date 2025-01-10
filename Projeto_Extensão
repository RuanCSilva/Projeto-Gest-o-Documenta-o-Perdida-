// Criação do projeto de gestão de documentos perdidos usando React Native

// Estrutura Inicial: Gerenciamento de Documentação Perdida
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';
import { View, Text, TextInput, Button, FlatList, StyleSheet } from 'react-native';

const Stack = createStackNavigator();

// Tela Principal
const HomeScreen = ({ navigation }) => {
  return (
    <View style={styles.container}>
      <Text style={styles.title}>Sistema de Gestão de Documentos Perdidos</Text>
      <Button
        title="Cadastrar Documento Perdido"
        onPress={() => navigation.navigate('Cadastro')}
      />
      <Button
        title="Buscar Documento"
        onPress={() => navigation.navigate('Busca')}
      />
    </View>
  );
};

// Tela de Cadastro
const CadastroScreen = ({ navigation }) => {
  const [descricao, setDescricao] = React.useState('');
  const [local, setLocal] = React.useState('');

  const handleCadastro = () => {
    // Lógica para registrar o documento perdido
    alert('Documento cadastrado com sucesso!');
    navigation.goBack();
  };

  return (
    <View style={styles.container}>
      <Text style={styles.subtitle}>Cadastro de Documento Perdido</Text>
      <TextInput
        placeholder="Descrição do documento"
        style={styles.input}
        value={descricao}
        onChangeText={setDescricao}
      />
      <TextInput
        placeholder="Local onde foi encontrado"
        style={styles.input}
        value={local}
        onChangeText={setLocal}
      />
      <Button title="Registrar" onPress={handleCadastro} />
    </View>
  );
};

// Tela de Busca
const BuscaScreen = () => {
  const [query, setQuery] = React.useState('');
  const [resultados, setResultados] = React.useState([]);

  const handleBusca = () => {
    // Lógica de busca no banco de dados fictício
    const mockData = [
      { id: '1', descricao: 'Carteira Preta', local: 'Praça Central' },
      { id: '2', descricao: 'RG José Silva', local: 'Shopping ABC' },
    ];
    const filtrados = mockData.filter((item) =>
      item.descricao.toLowerCase().includes(query.toLowerCase())
    );
    setResultados(filtrados);
  };

  return (
    <View style={styles.container}>
      <Text style={styles.subtitle}>Buscar Documento Perdido</Text>
      <TextInput
        placeholder="Digite o nome ou descrição"
        style={styles.input}
        value={query}
        onChangeText={setQuery}
      />
      <Button title="Buscar" onPress={handleBusca} />
      <FlatList
        data={resultados}
        keyExtractor={(item) => item.id}
        renderItem={({ item }) => (
          <View style={styles.listItem}>
            <Text>{item.descricao}</Text>
            <Text>Local: {item.local}</Text>
          </View>
        )}
      />
    </View>
  );
};

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Cadastro" component={CadastroScreen} />
        <Stack.Screen name="Busca" component={BuscaScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    padding: 20,
    justifyContent: 'center',
    alignItems: 'center',
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
  },
  subtitle: {
    fontSize: 18,
    marginBottom: 20,
  },
  input: {
    width: '100%',
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    padding: 10,
    marginBottom: 10,
  },
  listItem: {
    width: '100%',
    padding: 10,
    borderBottomWidth: 1,
    borderBottomColor: '#ccc',
  },
});

# Criando-um-App-Flutter-de-Lista-de-Contatos

Vamos criar um guia modular para desenvolver um App Flutter de Lista de Contatos, utilizando pacotes externos para enriquecer a aplicação.

---

### **Módulo 1: Preparação do Ambiente e Projeto**
Inicialmente, configure o ambiente Flutter e crie um novo projeto. Instale os pacotes necessários como `http`, `provider` e `sqflite` para gerenciamento de estado, banco de dados e consumo de API.

### **Módulo 2: Design da Interface de Usuário**
Desenhe a UI da aplicação. Utilize `ListView.builder` para criar uma lista rolável de contatos. Cada item da lista deve exibir informações básicas e uma foto.

### **Módulo 3: Gerenciamento de Estado com Provider**
Implemente o `Provider` para gerenciar o estado da aplicação. Crie modelos para os contatos e um `ChangeNotifier` para atualizar a UI quando os contatos forem adicionados ou removidos.

### **Módulo 4: Integração com Banco de Dados Local**
Use o `sqflite` para armazenar os contatos localmente. Crie funções para inserir, ler, atualizar e deletar contatos do banco de dados.

### **Módulo 5: Consumo de API para Obter Fotos**
Integre um serviço de API para obter fotos aleatórias para os contatos. Você pode usar a API `randomuser.me` para isso. Faça requisições assíncronas e atualize os contatos com as fotos recebidas.

### **Módulo 6: Funcionalidades Adicionais**
Adicione funcionalidades como busca, filtragem e ordenação dos contatos. Implemente a adição e remoção de contatos através de formulários.

### **Módulo 7: Testes e Validações**
Escreva testes para validar as funcionalidades da aplicação. Garanta que todos os componentes funcionem como esperado.

### **Módulo 8: Conclusão e Distribuição**
Finalize o app, faça uma revisão completa e prepare-o para distribuição. Publique o app na Google Play Store ou App Store.

---

Aqui está um exemplo prático de como integrar a API `randomuser.me` para obter fotos de contatos:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';

Future<String> fetchRandomUserPhoto() async {
  final response = await http.get(Uri.parse('https://randomuser.me/api/'));

  if (response.statusCode == 200) {
    final Map<String, dynamic> data = json.decode(response.body);
    String photoUrl = data['results'][0]['picture']['large'];
    return photoUrl;
  } else {
    throw Exception('Falha ao obter foto do usuário');
  }
}
```

Este código faz uma requisição `GET` para a API `randomuser.me` e retorna a URL de uma foto aleatória. Você pode usar essa URL para exibir a foto em seu app de lista de contatos.

Espero que este guia modular ajude você a criar seu App Flutter de Lista de Contatos.

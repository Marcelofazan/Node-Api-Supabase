## 🚀 API-NodeJS-RepositoryPattern-Supabase
Exemplo de criação de API em Node.js na arquitetura de camadas utilizando banco de dados Supabase.

#### O que voçê vai ver nesse Projeto
| Tecnologia | Descrição |
|-----------|-----------|
| **Supabase** | Wrapper (capa facilitadora) para simplificar o desenvolvimento com o banco de dados PostgreSQL  |
| **Client Supabase** | Instância de cliente que permite interagir com todos os serviços do Supabase |
| **.env** | Gerenciar variáveis de ambiente, garantindo segurança (não expor senhas/chaves) e flexibilidade entre ambientes (desenvolvimento, produção) |
| **Express JSON** |É um middleware embutido responsável por analisar (parsear) corpos de requisições HTTP recebidas que contenham dados no formato JSON. |
| **Express Router** | Reponsável por criar manipuladores de rotas modulares e montáveis.|
| **Sequelize** | Mapeador objeto-relacional (ORM) permite que manipular dados usando objetos e métodos JavaScript, eliminando a necessidade de escrever queries SQL.|

#### Requisitos e Detalhe do uso do Node.js
- Recuperar as dependencias do projeto node_modules . 
```bash
npm install express
```

- Automatizar o processo de inicialização
```bash
npm install -g nodemon
```

- Executar o Build do Projeto
```bash
nodemon index.js
ou 
node index.js
```

#### 🧪 Execução de Endpoints
**1 -Registrar paciente**
- Enviar POST / Paciente: **http://localhost:3333/paciente**, selecionar Guia Body -> escolher RAW e enviar o seguinte JSON 
   ```json
    { 
            "nome": "Pessoa 1", 
            "email": "email@email.com", 
            "telefone": "(99)99999-9999", 
            "endereco": "Rua endereço 1"
    }
   ```

**2 -Alterar paciente**
- Enviar PUT / Paciente: **http://localhost:3333/paciente**, selecionar Guia Body -> escolher RAW e enviar o seguinte JSON 
  ```json
    { 
            "pacienteId": 1, 
            "nome": "Pessoa 1 Alterado", 
            "email": "email@email.com", 
            "telefone": "(99)99999-9999", 
            "endereco": "Rua endereco 1"
    }
  ```

**3 -Registrar sessão**
- Enviar POST / Sessao: **http://localhost:3333/sessao**, selecionar Guia Body -> escolher RAW e enviar o seguinte JSON 
   ```json
    { 
            "pacienteId": 1,
            "data": "2028-04-22 13:30:00",
            "observacao": "Paciente está com sessão agendada",
            "valor": 150.50,
            "inPago": false
    }
  ```

**4 -Alterar sessão**
- Enviar PUT / Sessao: **http://localhost:3333/sessao**, selecionar Guia Body -> escolher RAW e enviar o seguinte JSON 
```json
    { 
            "sessaoId": 1,
            "data": "2028-04-22 13:30:00",
            "observacao": "Paciente está com sessão agendada",
            "valor": 104.50,
            "inPago": false
    }
```

#### Rotas dos métodos
| Metodo | Descrição |
|-----------|-----------|
| Metodo: POST |  /paciente |
| Metodo: PUT | /paciente |
| Metodo: DELETE |  /paciente/1 |
| Metodo: GET |  /paciente |
| Metodo: GET |  /paciente/likeNome?nome="Pessoa 1" |
| Metodo: POST |  /sessao |
| Metodo: PUT |  /sessao |
| Metodo: DELETE |  /sessao/1 |
| Metodo: GET |  /sessao/1 |
| Metodo: GET |  /sessao |


#### ⚠️ String de conexão do banco
Modifique a string de conexão no arquivo **db.js**, no trecho indicado:

```bash
const sequelize = new Sequelize('SEUBANCO', 'postgres', 'SUASENHA', {
host: 'localhost',
dialect: 'postgres',
define: {
	timestamps: false,
	},
```

O script para criação da tabela do exemplo encontra-se na pasta **Database**.


```markdown
# Sistema de Gerenciamento de Consultas Médicas

Este projeto é uma aplicação backend desenvolvida em **Node.js**, que gerencia um sistema de consultas médicas. Ele permite realizar operações de **criação**, **listagem**, **atualização** e **deleção** (CRUD) para as entidades de **Beneficiários**, **Médicos**, **Hospitais** e **Consultas**.

---

## 🚀 Tecnologias Utilizadas
- **Node.js**: Plataforma de desenvolvimento backend.
- **Express.js**: Framework para criação de APIs RESTful.
- **Sequelize ORM**: Para manipulação do banco de dados MySQL.
- **MySQL**: Banco de dados relacional.
- **Express-Validator**: Biblioteca para validação de dados.
- **dotenv**: Para gerenciamento de variáveis de ambiente.

---

## 📚 Funcionalidades

### CRUD para as Entidades:
1. **Beneficiário**  
   - Campos: `id`, `nome`, `email`, `data_nascimento`
2. **Médico**  
   - Campos: `id`, `nome`, `especialidade`, `hospital`
3. **Hospital**  
   - Campos: `id`, `nome`, `endereco`
4. **Consulta**  
   - Campos: `id`, `data`, `status`, `beneficiario`, `medico`, `hospital`

### Regras de Negócio:
1. **Beneficiário**: Não é permitido cadastrar beneficiários menores de 18 anos.
2. **Médico**: Cada médico deve estar associado a um hospital existente.
3. **Consulta**: Consultas concluídas não podem ser alteradas ou excluídas.

---

## ⚙️ Como Configurar o Projeto

### Pré-requisitos:
1. Node.js (v16 ou superior)
2. MySQL (com um banco de dados configurado)
3. Git

### Passo a Passo:
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/sistema-consultas.git
   cd sistema-consultas
   ```

2. **Instale as dependências**:
   ```bash
   npm install
   ```

3. **Configure o arquivo `.env`**:
   Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:
   ```plaintext
   DB_NAME=sistema_consultas
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   DB_HOST=localhost
   PORT=3000
   ```

4. **Configure o banco de dados**:
   Certifique-se de que o banco de dados MySQL esteja rodando e crie o banco especificado em `DB_NAME`.

5. **Inicie o servidor**:
   Em ambiente de desenvolvimento, utilize o seguinte comando:
   ```bash
   npm run dev
   ```
   Para produção:
   ```bash
   npm start
   ```

---

## 🛠️ Endpoints da API

### **Beneficiário**
- **POST** `/beneficiarios`: Cria um novo beneficiário.
- **GET** `/beneficiarios`: Lista todos os beneficiários.
- **PUT** `/beneficiarios/:id`: Atualiza um beneficiário existente.
- **DELETE** `/beneficiarios/:id`: Deleta um beneficiário.

### **Médico**
- **POST** `/medicos`: Cria um novo médico.
- **GET** `/medicos`: Lista todos os médicos.
- **PUT** `/medicos/:id`: Atualiza um médico existente.
- **DELETE** `/medicos/:id`: Deleta um médico.

### **Hospital**
- **POST** `/hospitais`: Cria um novo hospital.
- **GET** `/hospitais`: Lista todos os hospitais.
- **PUT** `/hospitais/:id`: Atualiza um hospital existente.
- **DELETE** `/hospitais/:id`: Deleta um hospital.

### **Consulta**
- **POST** `/consultas`: Cria uma nova consulta.
- **GET** `/consultas`: Lista todas as consultas.
- **PUT** `/consultas/:id`: Atualiza uma consulta (exceto se estiver concluída).
- **DELETE** `/consultas/:id`: Deleta uma consulta (exceto se estiver concluída).

---

## 🧪 Testando a API

### Usando o Postman ou Insomnia
1. Faça requisições aos endpoints listados na seção **Endpoints da API**.
2. Utilize o formato JSON para os dados enviados no corpo das requisições.

Exemplo de requisição **POST** para criar um beneficiário:
```json
POST /beneficiarios
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "data_nascimento": "1990-01-01"
}
```

---

## 🗃️ Estrutura do Projeto

```plaintext
sistema-consultas/
├── src/
│   ├── config/        # Configurações (banco de dados, ambiente)
│   ├── controllers/   # Lógica das rotas
│   ├── models/        # Definições das tabelas (ORM)
│   ├── routes/        # Rotas para cada entidade
│   └── validators/    # Regras de validação
├── .env               # Variáveis de ambiente
├── index.js           # Entrada principal do servidor
└── package.json
```

---

## 👥 Contribuindo
1. Faça um fork do projeto.
2. Crie uma branch para sua feature:
   ```bash
   git checkout -b minha-feature
   ```
3. Commit suas alterações:
   ```bash
   git commit -m "Adiciona minha nova feature"
   ```
4. Envie sua branch:
   ```bash
   git push origin minha-feature
   ```
5. Abra um Pull Request.

---

## 📄 Licença
Este projeto está sob a licença MIT. Sinta-se à vontade para utilizá-lo e modificá-lo.

Basta copiar e colar no arquivo `README.md` do seu repositório. 🚀

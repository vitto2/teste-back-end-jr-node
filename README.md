Claro! Aqui está o texto no formato desejado, com a estrutura semelhante à seção a partir de "instale as dependências":

---

# Sistema de Gerenciamento de Consultas Médicas

Este projeto é uma aplicação backend desenvolvida em Node.js, que gerencia um sistema de consultas médicas. Ele permite realizar operações de criação, listagem, atualização e deleção (CRUD) para as entidades de Beneficiários, Médicos, Hospitais e Consultas.

## Tecnologias Utilizadas

- Node.js: Plataforma de desenvolvimento backend.
- Express.js: Framework para criação de APIs RESTful.
- Sequelize ORM: Para manipulação do banco de dados MySQL.
- MySQL: Banco de dados relacional.
- Express-Validator: Biblioteca para validação de dados.
- dotenv: Para gerenciamento de variáveis de ambiente.

## Funcionalidades

CRUD para as entidades:
- Beneficiário: Campos `id`, `nome`, `email`, `data_nascimento`.
- Médico: Campos `id`, `nome`, `especialidade`, `hospital`.
- Hospital: Campos `id`, `nome`, `endereco`.
- Consulta: Campos `id`, `data`, `status`, `beneficiario`, `medico`, `hospital`.

Regras de Negócio:
1. Beneficiário: Não é permitido cadastrar beneficiários menores de 18 anos.
2. Médico: Cada médico deve estar associado a um hospital existente.
3. Consulta: Consultas concluídas não podem ser alteradas ou excluídas.

## Como Configurar o Projeto

### Pré-requisitos
1. Instale o Node.js na versão 16 ou superior.
2. Instale o MySQL e configure um banco de dados funcional.
3. Certifique-se de que o Git esteja instalado.

### Passo a Passo

1. Clone o repositório:  
   `git clone https://github.com/seu-usuario/sistema-consultas.git`  
   Navegue para a pasta do projeto:  
   `cd sistema-consultas`.

2. Instale as dependências do projeto:  
   `npm install`.

3. Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:  
   ```
   DB_NAME=sistema_consultas
   DB_USER=seu_usuario
   DB_PASSWORD=sua_senha
   DB_HOST=localhost
   PORT=3000
   ```

4. Configure o banco de dados MySQL com o nome especificado na variável `DB_NAME`. Certifique-se de que o servidor MySQL está em execução.

5. Inicie o servidor:  
   Em ambiente de desenvolvimento:  
   `npm run dev`.  
   Em ambiente de produção:  
   `npm start`.

## Endpoints da API

### Beneficiário
- POST `/beneficiarios`: Cria um novo beneficiário.
- GET `/beneficiarios`: Lista todos os beneficiários.
- PUT `/beneficiarios/:id`: Atualiza um beneficiário existente.
- DELETE `/beneficiarios/:id`: Deleta um beneficiário.

### Médico
- POST `/medicos`: Cria um novo médico.
- GET `/medicos`: Lista todos os médicos.
- PUT `/medicos/:id`: Atualiza um médico existente.
- DELETE `/medicos/:id`: Deleta um médico.

### Hospital
- POST `/hospitais`: Cria um novo hospital.
- GET `/hospitais`: Lista todos os hospitais.
- PUT `/hospitais/:id`: Atualiza um hospital existente.
- DELETE `/hospitais/:id`: Deleta um hospital.

### Consulta
- POST `/consultas`: Cria uma nova consulta.
- GET `/consultas`: Lista todas as consultas.
- PUT `/consultas/:id`: Atualiza uma consulta (exceto se estiver concluída).
- DELETE `/consultas/:id`: Deleta uma consulta (exceto se estiver concluída).

## Testando a API

Use ferramentas como Postman ou Insomnia para enviar requisições aos endpoints listados. Certifique-se de usar o formato JSON para os dados enviados no corpo das requisições.

Exemplo de requisição POST para criar um beneficiário:
```
POST /beneficiarios
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "data_nascimento": "1990-01-01"
}
```

## Estrutura do Projeto

O projeto segue a estrutura abaixo:

```
sistema-consultas/
├── src/
│   ├── config/        Configurações (banco de dados, ambiente)
│   ├── controllers/   Lógica das rotas
│   ├── models/        Definições das tabelas (ORM)
│   ├── routes/        Rotas para cada entidade
│   └── validators/    Regras de validação
├── .env               Variáveis de ambiente
├── index.js           Entrada principal do servidor
└── package.json
```

## Contribuindo

1. Faça um fork do projeto.  
2. Crie uma branch para sua feature:  
   `git checkout -b minha-feature`.  
3. Commit suas alterações:  
   `git commit -m "Adiciona minha nova feature"`.  
4. Envie sua branch:  
   `git push origin minha-feature`.  
5. Abra um Pull Request para revisão.

## Licença

Este projeto está sob a licença MIT. Sinta-se à vontade para utilizá-lo e modificá-lo.

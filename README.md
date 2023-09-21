# Nosso Mini Insta

## O que o usuário pode fazer

- Fazer login
- Fazer cadastro
- Ver os dados do seu perfil
- Editar os dados do seu perfil
- Ver postagens de outras pessoas
    - Ver quatidade de curtidas numa postagem
    - Ver os comentários em uma postagem
- Curtir postagens de outras pessoas
- Comentar em postagens

## O que não será possível fazer

- Ver a localização de uma postagem
- Ver pessoas que curtiram uma postagem
- Curtir um comentário
- Comentar em outros comentários

## Endpoints

### POST - Login

#### Dados enviados
- username
- senha

#### Dados retornados
- sucesso / erro
- token

---

### POST - Cadastro

#### Dados enviados
- username
- senha

#### Dados retornados
- sucesso / erro

---

### GET - Perfil

#### Dados enviados
- token (que terá id ou username)

#### Dados retornados
- URL da foto
- Nome
- Username
- Site
- Bio
- Email
- Telefone
- Genero

---

### POST - Perfil

#### Dados enviados
- token (que terá id ou username)
- URL da foto
- Nome
- Username
- Site
- Bio
- Email
- Telefone
- Genero

#### Dados retornados
- Sucesso ou erro

---

### GET - Postagens

#### Dados enviados
- token
- offset

#### Dados retornados
- Postagens []
    - id
    - foi curtido por mim
    - Usuario
        - URL da foto
        - username
        - é perfil oficial
    - Fotos []
    - quatidade de curtidas
    - Comentários []
        - username
        - texto
    - Data


---

### POST - Curtir

#### Dados enviados
- token (contem username ou id do usuario)
- id da postagem

#### Dados retornados
- sucesso ou erro

---

### POST - Comentar

#### Dados enviados
- token (contem username ou id do usuario)
- id da postagem
- texto

#### Dados retornados
- sucesso ou erro

## Como Usar
#### Pré-requisitos
- Certifique-se de ter o Node.js instalado na sua máquina.
- Configure um banco de dados PostgreSQL e atualize as informações de configuração no arquivo de configuração do banco de dados, se necessário.
#### Instalação
1. Clone o repositório:
```bash
git clone git@github.com:Rafaelsousacarv/api-mini-insta.git
```

2. Navegue até a pasta do projeto:
```bash
cd api-mini-insta
```
3. Instale as dependências:
```bash
npm install
```

4. Atualize o arquivo dadosSensiveisExemplo.js para dadosSensiveis.js com as informações de acesso do seu banco de dados.

5. Inicialize o servidor de desenvolvimento:
```bash
npm run dev
```

### Uso
- Certifique-se de que o servidor está em execução.
- Use ferramentas como o Postman ou faça solicitações HTTP para a API nos endpoints correspondentes.
- Consulte a documentação da API para obter detalhes sobre como usar cada recurso.

## Endpoints da API

### Autenticação de Usuário

- **POST /cadastro**: Cria um novo usuário no sistema.
- **POST /login**: Realiza o login do usuário com base nas credenciais fornecidas.

### Gerenciamento de Usuários

- **GET /perfil**: Obtém detalhes do usuário autenticado.
- **PUT /perfil**: Atualiza os detalhes do usuário autenticado.

### Transações Financeiras

- **GET /postagens**: Lista todas as postagens dos usuários.
- **POST /postagens**: Adiciona uma nova postagem.
- **POST /postagens/:postagemId/curtir**: Adiciona uma nova curtida.
- **POST /postagens/:postagemId/comentar**: Adiciona um novo comentario.

### Middlewares

- **Middleware de Autenticação**: Verifica se o usuário está autenticado antes de acessar os endpoints protegidos.
- **Middlewares de Validação**: Realiza a validação dos dados de entrada para garantir que estão corretos antes de processá-los.


# Gemini 

![Capa do Projeto Gemini](src/img/byte-img.png)

#### Gemini é um projeto que permite o upload, atualização e visualização de imagens, integrando com a API do Google Gemini para gerar descrições automáticas das imagens. O sistema utiliza o MongoDB para armazenamento das imagens e suas descrições, proporcionando uma maneira simples de interagir com imagens e seus metadados.

## Índice

- [Funcionalidades](#funcionalidades)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Endpoints da API](#endpoints-da-api)
- [Saiba Mais](#saiba-mais)
  
## 🔧 Funcionalidades

- **Cadastro de Imagem**: Envia uma imagem para o servidor.
- **Adicionar Descrição**: Permite adicionar uma descrição onde é gerada automaticamente pela API do Google Gemini.
- **Visualização de Imagens**: Exibe todas as imagens cadastradas, com suas respectivas descrições geradas pela API.

## 💻 Tecnologias Utilizadas

- **Node.js**: Para desenvolvimento do servidor backend.
- **Express**: Framework para construção da API RESTful.
- **MongoDB**: Banco de dados NoSQL utilizado para armazenar as imagens e suas descrições.
- **Multer**: Middleware para lidar com o upload de arquivos (imagens).
- **Google Gemini API**: Utilizada para gerar automaticamente as descrições das imagens.
- **CORS**: Para permitir requisições entre diferentes domínios.
- **Dotenv**: Para gerenciar variáveis de ambiente.

## 📥 Instalação

1. Clone o repositório:

```bash
git clone https://github.com/Bielhsn/instabytes.git
```

2. Acesse o diretório do projeto:
 ```bash
cd gemini
```
4. Instale as dependências:
 ```bash
npm install
```
5. Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis de ambiente:
 ```bash
MONGODB_URI=mongodb://localhost:27017/instabytes
GOOGLE_API_KEY=sua-chave-da-api-do-google
```
6. Inicie o servidor:
```bash
npm start
```
O servidor estará rodando em `localhost:3000`.

## 📡 Endpoints da API

### `GET /posts`.
Retorna todas as imagens cadastradas, incluindo o `_id`, `descricao`, `imgUrl` e `alt`.
```bash
[
  {
    "_id": "5f50c31b6c3c6c1f3b5d7c1d",
    "descricao": "Descrição da imagem gerada pelo Google Gemini.",
    "imgUrl": "http://localhost:3000/images/5f50c31b6c3c6c1f3b5d7c1d.png",
    "alt": "alt da imagem."
  },
  ...
]
```
### `POST /upload`.
Realiza o upload de uma nova imagem. A requisição deve incluir um arquivo de imagem no parâmetro `file`.
Exemplo de Requisição:

- **URL:** localhost:3000/upload
- **Método:** POST
- **Body (form-data):**
- **Key**: Imagem
- **file:**(Imagem)
```bash
{
    "acknowledged": true,
    "insertedId": "677da1250ef1aed550427943"
}
```
### `PUT /upload/:id`.
Atualiza a imagem existente. A requisição irá gerar uma descrição da imagem adicionada pelo método `POST`.
Exemplo de Requisição:

- **URL:** localhost:3000/upload/{id_da_imagem}
```bash
{
    "acknowledged": true,
    "modifiedCount": 1,
    "upsertedId": null,
    "upsertedCount": 0,
    "matchedCount": 1
}
```
## 🌟 Saiba Mais
- **Post do Projeto**: 

iniciar gerenciador de pacotes 
packge.json devera ir para a raiz do projeto
```
npm init -y 
```
instalar pacotes
```
npm i express nodemon dotenv
```
express: framework web para construção da infraestrutura da API;
nodemon: monitora as mudanças nos arquivos do projeto e reinicia automaticamente o servidor Node;
dotenv: gerencia as variáveis de ambiente dentro do projeto;
A confirmação da instalação dos pacotes pode ser vista na chave 'dependencies' no arquivo package.json, conforme imagem abaixo

Criar arquivo .gitignore
```
nano .gitignore
```
Com o comando nano, podemos criar e editar um arquivo pelo terminal
Ctrl + o: Salvar o arquivo
Enter: Confirmar
Ctrl + x: Fechar o arquivo
Este arquivo é utilizado para ignorar o envio de pastas e arquivos pro gitHub

Adicionar no arquivo .gitignore o nome da pasta criada após a instalação dos pacotes
```
node_modules
```
Esta pasta node_modules não precisamos enviar pro gitHub, pois pode ser recriada com o comando 'npm install'

Criar estrutura de arquivos e pastas
```
mkdir src
```
Criar arquivos dentro da pasta src
```
touch src/app.js
```
Arquivo responsável de criar a configuração da API
```
touch src/server.js
```
Arquivo responsável em receber as configurações da aplicação e rodar a API

Criar pastas dentro da pasta src
```
mkdir src/config
```

Pasta para gerenciar a conexão com o banco de dados
```
mkdir src/controllers
```

Pasta para gerenciar as requisições das rotas e conexão com banco de dados
```
mkdir src/routes
```

Pasta para gerenciar as rotas da API

Clonar o repositório na sua máquina
Abrir o gitBash em um local do computador
Digitar o comando 'git clone' junto com a URL do seu repositório
```
git clone URL_REPOSITORIO
```

Acessar pasta
Digitar o comando 'cd' e o nome do seu repositório
cd (change directory): acessar outra pasta
```
cd NOME_REPOSITORIO
```
Reinstalar os pacotes da aplicação
```
npm i
```
Este comando irá recriar a pasta node_modules no projeto
Criar pastas dentro da pasta src
```
mkdir src/routes
```

Criar arquivo dentro da pasta routes
```
touch src/routes/rotas.js
```
Responsável pelas rotas que serão acessadas na API
Abrir o VSCode
```
code .
```

Abrir o arquivo rotas.js e digitar os códigos
```
// Importar o modulo de Router do express
const { Router } = require('express');

// Instanciar o Router na variável router
const router = Router();

router.get('/listar', (request, response) => {
    response.send('Método GET: listar informações');
});
router.post('/cadastrar', (request, response) => {
    response.send('Método POST: salvar informações');
});
router.put('/user/:id', (request, response) => {
    response.send('Método PUT: atualizar informações');
});
router.delete('/user/:id', (request, response) => {
    response.send('Método DELETE: remover informações');
});

module.exports = router;
```

Abrir o arquivo app.js e adicionar o código
Precisamos importar o arquivo de rotas nas configurações da API
```
const router = require('./routes/rotas');
```
Habilitar as rotas na aplicação
Esta linha deve inserida depois da criação da variável app
```
app.use('/api', router);
```

Atualizar projeto no gitHub
Adicionar todos arquivos ao versionamento
```
git add .
```
Salvar projeto e escrever comentário sobre o processo realizado
```
git commit -m 'rotas do projeto'
```
Enviar os arquivos atualizados para o gitHub
```
git push
```
Recriacar arquivo .env e .env.example colocando a PORT = 3008 no visual code.
# Criando um projeto
* Para cria o projeto execute o seguinte comando no seu terminal (é necessário ter o nodeJs >= v20.20.0 instalado no pc/notebook):  
```
npx create-react-app react-basico

```
* Após criar a aplicação aparece o seguinte comando no seu terminal
```
Success! Created react-basico at /var/www/html/projetos/React/react-basico
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd react-basico
  npm start

Happy hacking!


```

* Estrutura básica no projeto react
```
    react-basico
        node_modules **(Esse diretório possui todos os módulos node)**
        public
            favicon.ico
            index.html **(<div id="root"></div> é o local que chama toda a aplicação)**
            logo192.png
            logo512.png
            manifest.json **(Parâmetros de configurações do nosso aplicativo)**
            robots.txt **(Arquivo de cofigurações de motores de busca)**
        src  **(Esse diretório é onde fica todo código da aplicação)**
            App.css **(CSS da aplicação)
            App.js  **(Arquivo principal, onde o aplicativo roda em <div className="App">)**
            App.test.js
            index.css
            index.js
            logo.svg
            reportWebVitals.js
            setupTests.js
        .gitignore **(Onde podemos ignorar ou permitir alguns arquivos e diretórios irem para o github)**
        package-lock.json
        package.json **(Onde fica todas as dependencias do nosso aplicativo)**
        README.md  **(Se quiser documentar a aplicação)**
```

* Alterando o arquivo App.js

```
  <header className="App-header">
    <img src={logo} className="App-logo" alt="logo" />
    <p>Olá,  meu primeiro projeto React</p>
  </header>

``
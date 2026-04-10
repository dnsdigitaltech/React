# Criando um projeto
* Instale a Extensão React Developer Tools no seu navegador  

* Criando componentes

Dentro do diretório src/components onde ficará todos nossos componentes

Dentro de components criar um arquivo chamado Comentario.js

A primeira coisa que tem que fazer no componente é importar o React que fica no diretório node_modules
```
import React from "react";

```

Logo após importar vamos criar nosso componente que nada mais que do que uma função java script
- OBS: os componetes sempre começa com a primeira letra em maiúscula.
```
  //JSX
  const Comentario = () => (
    <div>Olá eu sou um componente</div>
  );

  export default Comentario;

```

Perceba que coloquei o html dentro do java script, isse é chamado de JSX (JavaScript XML, uma sintaxe que usamos dentro do js como se fosse html).

* Usando  componentes
Após criar o componente poderá usar ele em outros lugares, vamos usar no App.js.
- OBS: para usar o componente é necessário importar o mesmo.
```
  import './App.css';
  import Comentario from './components/Comentario';

  function App() {
    return (
      <div className="App">
        <h1>Meu projeto</h1>
        <Comentario/>
      </div>
    );
  }

  export default App;

```
O componente é como se fosse uma tag html

```
<Comentario/>

```

Coloquei apanas a tag <Comentario/>, porém ele vai imprimir o que está dentro da tag, nesse caso:

```
<div>Olá eu sou um componente</div>

```
Podemos usar o componente várias vezes isso é muito bom no React

```
import './App.css';
import Comentario from './components/Comentario';

function App() {
  return (
    <div className="App">
      <h1>Meu projeto</h1>
      <Comentario/>
      <Comentario/>
      <Comentario/>
      <Comentario/>
    </div>
  );
}

export default App;

```

* O componente só poderá retornar um único elemento, observe o componente abaixo ele vai dar erro, pois possui dois elementos

```
import React from "react";

const Comentario = () => (
    <div>Davi</div>
    <div>Olá, tudo bem?</div>
);

export default Comentario;

```
Vai dar o seguinte erro:

```
Compiled with problems:
×
ERROR in ./src/components/Comentario.js
Module build failed (from ./node_modules/babel-loader/lib/index.js):
SyntaxError: /var/www/html/projetos/React/react-basico/src/components/Comentario.js: Adjacent JSX elements must be wrapped in an enclosing tag. Did you want a JSX fragment <>...</>? (6:4)

  4 | const Comentario = () => (
  5 |     <div>Davi</div>
> 6 |     <div>Olá, tudo bem?</div>
    |     ^
  7 | );
  8 |
  9 | export default Comentario;

```
**Solução para usar mais de um elemento no componete:**

- Solução 1:  colocar todos elementos dentro de uma div, porém existe uma div englobando todos elementos

```
import React from "react";

const Comentario = () => (
    <div>
        <div>Davi</div>
        <div>Olá, tudo bem?</div>
    </div>
);

export default Comentario;

```


- Solução 2:  usar fragmentos, para não usar a div englobando todos elementos

```
import React from "react";

const Comentario = () => (
    <>
        <div>Davi</div>
        <div>Olá, tudo bem?</div>
    </>
);

export default Comentario;

```

OBS: dependendo do componente você poderá usar uma div, p, ou outro tipo de tag


* Colocando um estilo no companente

Usando a forma simples do css criando dentro do diretório components um arquivo chamado Comentario.css, depois basta importar e usar o arquivo

```
import React from "react";
import './Comentario.css';
const Comentario = () => (
    <div class="Comentario">
        <div>Davi</div>
        <div>Olá, tudo bem?</div>
    </div>
);

export default Comentario;

```

Se for no console do navegar vai aparecer o seguinte erro:

```
Invalid DOM property `class`. Did you mean `className`? installHook.js:1 

```
Ocorreu esse erro, pois ele está entendendo que a class chamanda ai é uma palavra pra gerar Classes como no exemploa abaixo, esse css até funcionou, mas não é a forma correta de chamar classes css.

```
import React from "react";
import './Comentario.css';

class Classes { }//é como se estivessémos chamando essa class no java script

const Comentario = () => (
    <div class="Comentario">
        <div>Davi</div>
        <div>Olá, tudo bem?</div>
    </div>
);

export default Comentario;

```
Temos que entender que no java scritp possui alaguma restrições de alguns nomes ex: class, nesse caso usaremos className, utilizando dessa forma não dará mais erro no console

```

import React from "react";
import './Comentario.css';

const Comentario = () => (
    <div className="Comentario">
        <div>Davi</div>
        <div>Olá, tudo bem?</div>
    </div>
);

export default Comentario;

``

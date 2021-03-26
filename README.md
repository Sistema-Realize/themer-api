[![Logo Realize](https://realize.pro.br/exemplo-material-didatico/github/logo-realize.png)](https://www.realize.pro.br/)

Biblioteca para **criação de temas** para o sistema [Realize](https://www.realize.pro.br) 🛠

*#JAVASCRIPT #HTML #CSS*

## Sumário

- [Descrição](#descrição)
- [Instalação](#instalação) - [[🎬 Vídeo Tutorial](https://www.loom.com/share/78e91232647b43a7803363cb4e392224)]
  - [Primeiros passos](#primeiros-passos)
  - [Setup Inicial](#setup-inicial)
- [Documentação](#documentação)
  - [Desabilitar Menu de Navegação](#desabilitar-menu-de-navegação) - [[🎬 Vídeo Tutorial](https://www.loom.com/share/fbd4fc649b354719afe9eb9f842b53ad)]
    - [Theme.setMenu(boolean)](#setmenu)
  - [Adicionar Recursos Pré-existentes](#adicionar-recursos-pré-existentes) - [[🎬 Vídeo Tutorial](https://www.loom.com/share/7fe116295ccd4d219165640dc0f21898)]
    - [Theme.addPlugin(string)](#addplugin)
  - [Criar Novos Recursos](#criar-novos-recursos) - [[🎬 Vídeo Tutorial 1/3](https://www.loom.com/share/465f7ded66d14c078439f229d480146d)] [[🎬 Vídeo Tutorial 2/3](https://www.loom.com/share/539f5de7522b4a6b827a1d921c48ee5c)] [[🎬 Vídeo Tutorial 3/3](https://www.loom.com/share/440f662c8a4945fea9003f14c1bc6de6)]
    - [Criar Grupo](#criar-grupo)
      - [Theme.addGroup(string,function)](#addgroup)
    - [Criar Recurso](#criar-recurso)
      - [group.addResource(string,function)](#addresource)
    - [Criar Campo](#criar-campo)
      - [resource.addEditor(string,function)](#addeditor)
      - [resource.addText(string,function)](#addtext)
      - [resource.addImage(string,function)](#addimage)
      - [resource.addColor(string,function)](#addcolor)
    - [Criar Shortcode](#criar-shortcode)
      - [field.shortcode(string)](#shortcode)
    - [Criar Resultado do Recurso](#criar-resultado-do-recurso)
  - [Invocar Funções por Eventos](#invocar-funções-por-eventos) - [[🎬 Vídeo Tutorial](https://www.loom.com/share/b369c5a548c74d75a75eebd5a989b52c)]
    - [Theme.addHook(string,function)](#addhook)
  - [Subir Tema na Realize](#subir-tema-na-realize) - [[🎬 Vídeo Tutorial](https://www.loom.com/share/6d82423056ff4f1895831f9f26b93c5f)]
    - [Theme.download()](#download)

## Descrição

É com muito prazer que informamos que nossa plataforma de construção de Materiais Didáticos, a [Realize](https://www.realize.pro.br), agora possui a viabilidade de **construção de temas** 👏👏👏👏. O tema é o modelo visual e interativo do material didático no qual o conteúdo bruto será construído. Veja o exemplo [clicando aqui](https://realize.pro.br/exemplo-material-didatico/).

Conforme a imagem abaixo, quando os autores escrevem o conteúdo bruto no lado esquerdo do editor, a Inteligência [Realize](https://www.realize.pro.br) constrói o material didático, contendo o tema, no lado direito do editor.

![Editor da Realize](https://realize.pro.br/exemplo-material-didatico/github/editor.png)

É no tema onde o aluno terá contato com o design, interatividade e recursos educacionais, o que é peça chave para que ele **valorize a sua experiência e reconheça o valor agregado do ensino de seu conteúdo** 🤩🤩🤩🤩.

Atualmente a **concorrência das instituições no ensino** não é apenas contra outras instituições, mas contra todo um universo midiático de youtube, plataformas de ensino livre, interações gamificadas e elaboradas.

> O tema, ao potencializar a experiência educacional e o aprendizado dos seus alunos, é um diferencial perante a concorrência.
> - [Gustavo Lima, CTO](https://www.linkedin.com/in/gustavomdcl/)

Sendo assim, utilizando essa biblioteca, você poderá:

- Transformar o seu arquivo HTML em um tema **compatível com o sistema [Realize](https://www.realize.pro.br)**;
- Configurar as **diferentes funcionalidades** do seu tema;
- Adicionar **recursos pré-existentes** no seu tema;
- Criar **novos recursos** para o seu tema.

Nós da [Realize](https://www.realize.pro.br) também podemos criar temas completamente do zero com diferentes tipos de personalizações. Caso tenha interesse, entre em contato com **contato@realize.pro.br**.

## Instalação

⚠️  Essa biblioteca utiliza a linguagem *javascript* e funciona em arquivos *html*.  ⚠️

🎬 Assista nosso [Vídeo Tutorial](https://www.loom.com/share/78e91232647b43a7803363cb4e392224).

### Primeiros passos

Antes de iniciar o processo de instalação da biblioteca, você deve certificar de que há um arquivo `index.html` na pasta raiz do seu projeto.

![Arquivo index.html na pasta raiz do projeto](https://realize.pro.br/exemplo-material-didatico/github/pastaraiz.png)

Provavelmente o seu conteúdo será parecido com esse:

```html
<!DOCTYPE html>
<html lang="pt">
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
  </head>
  <body>
    
    ...
    
  </body>
</html>
```

Baixe o arquivo [`realize.min.js`](https://github.com/Sistema-Realize/themer-api/blob/main/realize.min.js) e o inclua na pasta raiz do seu projeto:

![Arquivo realize.min.js na pasta raiz do projeto](https://realize.pro.br/exemplo-material-didatico/github/javascriptrealize.png)

Importe o arquivo [`🔗 realize.min.js`](https://github.com/Sistema-Realize/themer-api/blob/main/realize.min.js) no código `index.html` a partir da tag `<script src="realize.min.js"></script>`, e o inclua antes do fechamento de `</body>` conforme abaixo:

```html
<!DOCTYPE html>
<html lang="pt">
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
  </head>
  <body>

    <script src="realize.min.js"></script>
    
  </body>
</html>
```

Pronto, agora já podemos trabalhar com a biblioteca!

### Setup Inicial

Para iniciar a utilização da biblioteca, será necessário fazer a configuração inicial. O arquivo [`realize.min.js`](https://github.com/Sistema-Realize/themer-api/blob/main/realize.min.js), quando importado em seu `index.html`, fornece uma variável global `Realize`, que será manipulada por nós para controlar as funções da biblioteca, inclusive a configuração inicial.

Sendo assim, após a inclusão da tag `<script src="realize.min.js"></script>`, será necessário criar uma nova tag `<script></script>` para manipular a variável `Realize`. Para que isso seja feito após o carregamento correto de todos os scripts da página, inserimos todo o nosso código sempre dentro da função `window.onload = function(){});`.

A variável `Realize` possui uma função inicial `Realize.run()` que exporta uma classe que, por sua vez, será usada para criar o nosso tema. Nossa primeira ação será instanciar uma variável com o valor dessa função inicial, como `var Theme = Realize.run();`.

Após criar a variável `Theme` é necessário iniciar o tema com a função `Theme.init();`.

```html
<!DOCTYPE html>
<html lang="pt">
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
  </head>
  <body>

    <script src="realize.min.js"></script>
    <script>
      window.onload = function(){
        var Theme = Realize.run();
        Theme.init();
      };
    </script>
    
  </body>
</html>
```

Assim, as configurações em *javascript* iniciais estão prontas, mas ainda falta informar no *html* onde o **conteúdo** e o **menu de navegação** serão criados. 

O **conteúdo** é representado pelo texto digitado pelo professor no **Editor**, que fica do lado direito da interface na [Realize](https://www.realize.pro.br):

![Editor da Realize](https://realize.pro.br/exemplo-material-didatico/github/editor.png)

Esse **conteúdo** é separado em tópicos, que são divididos no tema em páginas no **menu de navegação**.

Para incluir esses dois elementos no html, é preciso adicionar a class `.realize-menu` para o **menu de navegação** e a class `.realize-content` para o **conteúdo** em duas `<div></div>` cada, conforme abaixo:

```html
<!DOCTYPE html>
<html lang="pt">
  <head>
    <meta charset="UTF-8">
    <title>Document</title>
  </head>
  <body>
    
    <div class="realize-menu"></div>
    <div class="realize-content"></div>

    <script src="realize.min.js"></script>
    <script>
      window.onload = function(){
        var Theme = Realize.run();
        Theme.init();
      };
    </script>
    
  </body>
</html>
```

Após incluir esses dois elementos, é possível testar esse arquivo `index.html` no seu servidor local e verificar que foram criados tanto um **conteúdo**, quanto um **menu de navegação**, com textos falsos para que você possa visualizar seu tema e personalizar o CSS de cada elemento.

## Documentação

### Desabilitar Menu de Navegação

 🎬 Assista nosso [Vídeo Tutorial](https://www.loom.com/share/fbd4fc649b354719afe9eb9f842b53ad).

A divisão de tópicos em páginas já é padrão nessa biblioteca. Entretanto, é possível carregar todo o **conteúdo** em apenas uma página, mesmo se houver tópicos diferentes, desabilitando assim o **menu de navegação** e sua separação em items. Para isso, basta inserir a função `Theme.setMenu(false);`, conforme o código abaixo:

```js
var Theme = Realize.run();
Theme.setMenu(false);
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`. Caso o valor seja `false`, não será mais necessário incluir o elemento `<div class="realize-menu"></div>` no *html*. 

#### setMenu()

```js
Theme.setMenu(boolean)
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| boolean | `true` | Habilita o menu de navegação, cada tópico é apresentado em uma página própria |
| boolean | `false` | Desabilita o menu de navegação, todos os tópicos são carregados de uma vez |

### Adicionar Recursos Pré-existentes

🎬 Assista nosso [Vídeo Tutorial](https://www.loom.com/share/7fe116295ccd4d219165640dc0f21898)

Na [Realize](https://www.realize.pro.br) existe a possibilidade de inserir recursos no **conteúdo**. Esses recursos são definidos por formulários em que o usuário insere informações que são convertidas em algum recurso no nosso tema. Nos exemplos abaixo é possível verificar a inserção do recurso *Sanfona* no **conteúdo** da unidade e o seu formulário, em ordem:

![Editor de texto com recurso sanfona](https://realize.pro.br/exemplo-material-didatico/github/editorcomsanfona.png)

![Formulário para criar o recurso sanfona](https://realize.pro.br/exemplo-material-didatico/github/formulariosanfona.png)

Existem alguns recursos pré-definidos que você pode incluir no seu tema, que estão listados abaixo:

- **iframe**: Inserir uma tag `<iframe src=""/>` para incluir algum elemento externo.
- **figura**: Inserir título, fonte, texto de acessibilidade e arquivo de imagem. [Exemplo](https://www.youtube.com/watch?v=UPNhNIGLK74)
- **video**: Inserir um link do *youtube/vimeo* ou subir um arquivo de vídeo. [Exemplo](https://www.youtube.com/watch?v=THNmYJlZtWA)
- **podcast**: Inserir o código de compartilhamento do *soundcloud* ou subir um arquivo de áudio. [Exemplo](https://www.youtube.com/watch?v=pdH1lLAntLQ)
- **flipcard**: Inserir um texto que é apresentado por interação do usuário a partir de `mouseover` sobre um ícone de `+`. [Exemplo](https://www.youtube.com/watch?v=o0Xp8H0pLnw)
- **flipper**: Inserir um texto e uma imagem que é apresentado como um cartão de dois lados, onde a interação do usuário de clicar na imagem faz o cartão virar apresentando o texto. [Exemplo](https://www.youtube.com/watch?v=jojFXTKKoNs)
- **accordion**: Inserir um texto e uma imagem que é apresentado como dois cartões sobrepostos, onde a interação do usuário de clicar na imagem faz ela ser arrastada para a esquerda apresentando o texto abaixo. [Exemplo](https://www.youtube.com/watch?v=rBvBghc_AuA)
- **sanfona**: Inserir um título e um texto que é apresentado como um bloco contendo o título, que ao clicado, expande o conteúdo logo abaixo. [Exemplo](https://www.youtube.com/watch?v=5ddL-R91LVA)
- **objetiva**: Inserir um enunciado, um texto e alternativas que é apresentado como uma questão objetiva. [Exemplo](https://www.youtube.com/watch?v=kFVAl6C8BAg)
- **multipla**: Inserir um enunciado, um texto e alternativas que é apresentado como uma questão multipla respostas. [Exemplo](https://www.youtube.com/watch?v=wkVAFuxpJwk)

Para incluir tais recursos em seu tema, como por exemplo os recursos **sanfona** e **podcast**, basta incluí-los como `string`, separados por espaço, na função `Theme.addPlugin('sanfona podcast');`. O código abaixo exemplifica a inclusão de todos os recursos:

```js
var Theme = Realize.run();
Theme.addPlugin('iframe figura video podcast flipcard flipper accordion sanfona objetiva multipla');
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após incluir diferentes recursos, é possível testá-los ao abrir o arquivo `index.html` no seu servidor local e verificar que foram criados no **conteúdo**, com textos falsos para que você possa visualizar e personalizar o CSS de cada recurso.

#### addPlugin()

```js
Theme.addPlugin(string)
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'iframe figura video podcast flipcard flipper accordion sanfona objetiva multipla'` | Adiciona recursos, separados por espaço, no tema |

### Criar Novos Recursos

🎬 Assista nossos vídeos tutoriais, separados em 3 partes:
- [Vídeo Tutorial 1/3](https://www.loom.com/share/465f7ded66d14c078439f229d480146d)
- [Vídeo Tutorial 2/3](https://www.loom.com/share/539f5de7522b4a6b827a1d921c48ee5c)
- [Vídeo Tutorial 3/3](https://www.loom.com/share/440f662c8a4945fea9003f14c1bc6de6)

Na [Realize](https://www.realize.pro.br) existe a possibilidade de inserir recursos no **conteúdo**. Esses recursos são definidos por formulários em que o usuário insere informações que são convertidas em algum recurso no nosso tema. Nos exemplos abaixo é possível verificar a inserção do recurso *Sanfona* no **conteúdo** da unidade e o seu formulário, em ordem:

![Editor de texto com recurso sanfona](https://realize.pro.br/exemplo-material-didatico/github/editorcomsanfona.png)

![Formulário para criar o recurso sanfona](https://realize.pro.br/exemplo-material-didatico/github/formulariosanfona.png)

#### Criar Grupo

Cada recurso é organizado dentro de um **grupo**. Por exemplo, o recurso *Sanfona* é organizado dentro do grupo *Listas*, conforme a imagem abaixo. Um grupo pode ter diferentes recursos, mas um recurso sempre terá um grupo.

![Grupos de recursos e recursos](https://realize.pro.br/exemplo-material-didatico/github/gruposderecursos.png)

Para criar um novo recurso em seu tema é preciso primeiramente incluir um grupo pela função `Theme.addGroup();`. O código abaixo exemplifica a criação de um novo grupo *Destaques*:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){});
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após adicionar um grupo note que o segundo argumento da função `Theme.addGroup()` é uma função `function(group){}` que instancia o valor `group` como argumento. A partir desse valor será adicionado um recurso, que continua em [Criar Recurso](#criar-recurso).

##### addGroup()

```js
Theme.addGroup(string,function)
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do grupo |
| function | `function(group){}` | Adiciona uma função cujo argumento `group` é utilizado para criar recursos com a função `group.addResource(string,function)` |

#### Criar Recurso

Após adicionar um grupo note que o segundo argumento da função `Theme.addGroup()` é uma função `function(group){}` que instancia o valor `group` como argumento. A partir desse valor você pode adicionar mais de um recurso pela função `group.addResource();`. O código abaixo exemplifica a criação de dois novos recursos, *Destaque Total* e *Destaque Técnico*:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){
  group.addResource('Destaque Total',function(resource){});
  group.addResource('Destaque Técnico',function(resource){});
});
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após adicionar um recurso note que o segundo argumento da função `group.addResource()` é uma função `function(resource){}` que instancia o valor `resource` como argumento. A partir desse valor `resource` será adicionado um campo, que continua em [Criar Campo](#criar-campo).

##### addResource()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function);
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do recurso |
| function | `function(resource){}` | Adiciona uma função cujo argumento `resource` é utilizado para criar campos, como por exemplo um campo de Editor, com a função `resource.addEditor(string,function)` |

#### Criar Campo

Após adicionar um recurso note que o segundo argumento da função `group.addResource()` é uma função `function(resource){}` que instancia o valor `resource` como argumento. A partir desse valor você pode adicionar mais de um campo pelas funções abaixo:

- `resource.addEditor();`: Adiciona um Editor de texto, como um `<textarea/>` potencializado que dá a possibilidade de inserir parágrafos, listas, tabelas, formatação de texto, dentre outros. 
- `resource.addText();`: Adiciona um campo texto simples com **bold** e *itálico*, sem parágrafos, listas, tabelas, formatação de texto.
- `resource.addImage();`: Adiciona um campo para subir um arquivo de imagem.
- `resource.addColor();`: Adiciona um campo para selecionar uma cor. 

O código abaixo exemplifica a inserção de campos em dois novos recursos, *Destaque Total* e *Destaque Técnico*:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){
  group.addResource('Destaque Total',function(resource){
    resource.addEditor('Destaque',function(field){});
    resource.addText('Título',function(field){});
    resource.addImage('Arquivo',function(field){});
    resource.addColor('Cor de texto',function(field){});
  });
  group.addResource('Destaque Técnico',function(resource){
    resource.addEditor('Destaque',function(field){});
  });
});
Theme.init();
```

No recurso *Destaque Total* os campos adicionados foram:
- *Destaque*, como **editor**.
- *Título*, como **text**.
- *Arquivo*, como **image**.
- *Cor de Texto*, como **color**.

No recurso *Destaque Técnico* os campos adicionados foram:
- *Destaque*, como **editor**.

Essa função deve ser incluida antes da função `Theme.init();`.

Após adicionar um campo note que o segundo argumento das funções `resource.addEditor(field)`, `resource.addText(field)`, `resource.addImage(field)` ou `resource.addColor(field)` é uma função `function(field){}` que instancia o valor `field` como argumento. A partir desse valor `field` será adicionado um shortcode, que continua em [Criar Shortcode](#criar-shortcode).

##### addEditor()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addEditor(string,function);
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do campo |
| function | `function(field){}` | Adiciona uma função cujo argumento `field` é utilizado para criar shortcodes com a função `field.shortcode(string)` |

##### addText()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addText(string,function);
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do campo |
| function | `function(field){}` | Adiciona uma função cujo argumento `field` é utilizado para criar shortcodes com a função `field.shortcode(string)` |

##### addImage()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addImage(string,function);
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do campo |
| function | `function(field){}` | Adiciona uma função cujo argumento `field` é utilizado para criar shortcodes com a função `field.shortcode(string)` |

##### addColor()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addColor(string,function);
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'nome'` | Adiciona o nome do campo |
| function | `function(field){}` | Adiciona uma função cujo argumento `field` é utilizado para criar shortcodes com a função `field.shortcode(string)` |

#### Criar Shortcode

Após adicionar um campo note que o segundo argumento das funções `resource.addEditor(field)`, `resource.addText(field)`, `resource.addImage(field)` ou `resource.addColor(field)` é uma função `function(field){}` que instancia o valor `field` como argumento. A partir desse valor você pode adicionar um shortcode pela função `field.shortcode()`. 

Shortcodes, quando inseridos entre colchetes `[]` no [resultado final do recurso](#criar-resultado-do-recurso) `resource.build();`, servem para substituir o que o usuário preencheu no campo do formulário na [Realize](https://realize.pro.br).

Por exemplo, se o shortcode criado foi `field.shortcode('NOME')`, se o [resultado final do recurso](#criar-resultado-do-recurso) for `resource.build('<div>[NOME]</div>');`, se o que o usuário preencheu no campo for `João Gabriel`, o resultado será `<div>João Gabriel</div>`.

O código abaixo exemplifica a inserção de shortcodes em cada campo:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){
  group.addResource('Destaque Total',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
    resource.addText('Título',function(field){
      field.shortcode('TITLE');
    });
    resource.addImage('Arquivo',function(field){
      field.shortcode('IMAGE');
    });
    resource.addColor('Cor de texto',function(field){
      field.shortcode('COR');
    });
  });
  group.addResource('Destaque Técnico',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
  });
});
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após adicionar um shortcode saiba que ele será usado entre colchetes `[]` na função `resource.build();`, presente no [resultado final do recurso](#criar-resultado-do-recurso), para substituir o valor que o usuário preencher no formulário do recurso. 

##### shortcode()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addEditor(string,function(field){
      field.shortcode(string);
    });
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'shortcode'` | Adiciona um texto que, entre colchetes, na função `resource.build();`, será substituido pelo valor que o usuário preencheu no formulário do recurso. |

#### Criar Resultado do Recurso

Após adicionar um recurso note que o segundo argumento da função `group.addResource()` é uma função `function(resource){}` que instancia o valor `resource` como argumento. Para cada recurso adicionado, a partir desse valor, você deve adicionar um único resultado do recurso pela função `resource.build()`.

Um resultado do recurso nada mais é do que o código em *html* do que os campos do recurso irão construir. Cada campo será composto pelo valor incluido na função `field.shortcode()` entre colchetes. Esse valor será preenchido pelo preenchimento do campo no formulário do recurso.

A função `resource.build()` deve ser inserida após a criação de todos os campos.

O código abaixo exemplifica a inserção de um resultado em cada um dos dois recursos, *Destaque Total* e *Destaque Técnico*:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){
  group.addResource('Destaque Total',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
    resource.addText('Título',function(field){
      field.shortcode('TITLE');
    });
    resource.addImage('Arquivo',function(field){
      field.shortcode('IMAGE');
    });
    resource.addColor('Cor de texto',function(field){
      field.shortcode('COR');
    });
    resource.build('<div class="destaque-total">'+
      '<h1>[TITLE]</h1>'+
      '<div style="color:[COR];">[HIGHLIGHT]</div>'+
      '<img src="[IMAGE]" />'+
    '</div>');
  });
  group.addResource('Destaque Técnico',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
    resource.build('<div class="destaque-tecnico">[HIGHLIGHT]</div>');
  });
});
Theme.init();
```

Também é possível manipular, de forma avançada, os valores preenchidos no formulário e os elementos do DOM de cada resultado de recurso a partir de um segundo argumento da função `resource.build()`. Esse segundo argumento é opcional e é definido por uma função `resource.build(string,function(result){})` que instancia um argumento `result`. Esse argumento `result` é definido por um objeto composto por:

```js
{
  element: this // elemento pai da DOM do resultado do recurso, em javascript puro
  $element: $(this) // elemento pai da DOM do resultado do recurso, em jquery
  value: { shortcode: value } // todos os shortcodes, e seu resultado preenchido do formulário pelo usuário, em objeto
}
```

Essa manipulação é mais avançada para criar recursos mais complexos, tornando assim possível criar `addEventListener` de cada elemento, além do tratamento mais personalizado de cada valor.

O código abaixo exemplifica a inserção de uma manipulação mais complexa de um resultado do recurso *Destaque Técnico*:

```js
var Theme = Realize.run();
Theme.addGroup('Destaques',function(group){
  group.addResource('Destaque Total',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
    resource.addText('Título',function(field){
      field.shortcode('TITLE');
    });
    resource.addImage('Arquivo',function(field){
      field.shortcode('IMAGE');
    });
    resource.addColor('Cor de texto',function(field){
      field.shortcode('COR');
    });
    resource.build('<div class="destaque-total">'+
      '<h1>[TITLE]</h1>'+
      '<div style="color:[COR];">[HIGHLIGHT]</div>'+
      '<img src="[IMAGE]" />'+
    '</div>');
  });
  group.addResource('Destaque Técnico',function(resource){
    resource.addEditor('Destaque',function(field){
      field.shortcode('HIGHLIGHT');
    });
    resource.build('<div class="destaque-tecnico">[HIGHLIGHT]</div>',function(result){
      result.element.style.background = 'red';
      result.$element.click(function(e){
        e.preventDefault();
        result.$element.css('background','blue');
        console.log('value',result.value);
        alert(JSON.stringify(result.value));
      });
    });
  });
});
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após adicionar um resultado do recurso é possível testá-lo ao abrir o arquivo `index.html` no seu servidor local e verificar que foi criado no **conteúdo**, com textos falsos para que você possa visualizar e personalizar o CSS de cada recurso. Observe que cada texto falso substitui o shortcode criado para cada campo.

##### build()

```js
Theme.addGroup(string,function(group){
  group.addResource(string,function(resource){
    resource.addEditor(string,function(field){
      field.shortcode(string);
    });
    resource.build(string,function);
  });
});
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'<tag>[shortcode]</tag>'` | Adiciona uma string que contém um *html* que, com o shortcode do campo entre colchetes, será substituido pelo valor que o usuário preencheu no formulário do recurso. |
| function | `function(result){}` | Argumento não obrigatório. Adiciona uma função cujo argumento `result` é utilizado para manipular o elemento pai do resultado do recurso. <br /><br /> - `result.element` representa o elemento pai da DOM do resultado do recurso, em javascript puro; <br /> - `result.$element` representa o elemento pai da DOM do resultado do recurso, em jquery; <br /> - `result.value` representa um objeto com todos os shortcodes, e seu resultado preenchido do formulário pelo usuário |

### Invocar Funções por Eventos

🎬 Assista nosso [Vídeo Tutorial](https://www.loom.com/share/b369c5a548c74d75a75eebd5a989b52c)

Caso você precise invocar funções a partir de eventos da biblioteca, existe a função `Theme.addHook()`. Existem dois eventos abordados nessa função:

- **content**: Invocar uma função após o carregamento do conteúdo de cada página do menu. Se a função `Theme.setMenu(false);` for acionada, será invocado após carregamento do conteúdo.
- **end**: Invocar uma função após o carregamento da biblioteca.

Abaixo segue o exemplo para a aplicação de cada um dos dois eventos:

```js
var Theme = Realize.run();
Theme.addHook('end',function(){
  alert('Carregamento da biblioteca finalizado.');
});
Theme.addHook('content',function(){
  alert('Carregamento do conteúdo finalizado.');
});
Theme.init();
```

Essa função deve ser incluida antes da função `Theme.init();`.

Após invocar uma função por evento é possível testá-la ao abrir o arquivo `index.html` no seu servidor local.

#### addHook()

```js
Theme.addHook(string,function);
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| string | `'end'` | Invoca a função `function` do segundo argumento após o carregamento da biblioteca |
| string | `'content'` | Invoca a função `function` do segundo argumento após o carregamento do conteúdo |
| function | `function(){}` | Função invocada no evento informado no primeiro argumento `string` |

### Subir Tema na Realize

🎬 Assista nosso [Vídeo Tutorial](https://www.loom.com/share/6d82423056ff4f1895831f9f26b93c5f).

Agora que você **construiu** e **testou** o seu tema, chegou a hora de subir na [Realize](https://realize.pro.br/).

Primeiro você deve se certificar de que a sua **Unidade**, **Disciplina**, **Área** ou **Projeto** estão com o tema *Themer* selecionado, conforme a imagem abaixo:

![Tema Themer selecionado](https://realize.pro.br/exemplo-material-didatico/github/themer.png)

Depois disso, entre no modo de personalização da sua **Unidade**, **Disciplina**, **Área** ou **Projeto**. Observe que há dois envios de arquivos obrigatórios. O primeiro, chamado *Enviar Arquivo* e o segundo chamado *Configuração*, conforme a imagem abaixo:

![Envio de arquivos](https://realize.pro.br/exemplo-material-didatico/github/enviodearquivos.png)

No primeiro campo *Enviar Arquivo* você deve enviar um arquivo comprimido com formato `.zip` da raiz do seu projeto. No exemplo abaixo, observe que você não pode *zipar* a `projeto`, e sim todos os arquivos presentes na raiz dessa pasta. O seu `index.html` deve estar na raiz desse arquivo comprimido, se não, o seu tema não irá funcionar.

![Comprimindo arquivos na pasta raiz](https://realize.pro.br/exemplo-material-didatico/github/arquivosraiz.png)

No segundo campo *Configuração* você deve enviar um arquivo com formato `.json` que é exportado pelo seu próprio tema. Para iniciar a sua exportação, após a inserção da função `Theme.init();` você deve inserir a função `Theme.download();`, conforme o exemplo abaixo. 

```js
var Theme = Realize.run();
Theme.init();
Theme.download();
```

Após inserir a função `Theme.download();`, você deve abrir o seu arquivo `index.html` no seu servidor local. Ao fazer isso, o seu navegador irá automaticamente baixar um arquivo chamado `configuration.json`. É esse arquivo que você deve subir no campo *Configuração*. Agora você pode comentar a função `Theme.download();` para evitar que o seu código continue fazendo download a cada carregamento da página, conforme o exemplo abaixo.

```js
var Theme = Realize.run();
Theme.init();
// Theme.download();
```

Com os dois arquivos inseridos você já pode ir no **Editor** da [Realize](https://realize.pro.br/), salvar o seu conteúdo, visualizar o seu tema e testar os seus recursos criados. Caso precise fazer algum ajuste no seu tema, basta subir novamente os campos *Enviar Arquivo* e *Configuração* na personalização.

#### download()

```js
Theme.download();
```

| Argumento | Valor | Descrição |
| :--- | :---: | :--- |
| nenhum | | Não há argumentos |
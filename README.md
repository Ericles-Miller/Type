# **Visão geral do TypeScript**

O JavaScript, uma das linguagens de programação mais usadas do mundo, tornou-se a linguagem de programação oficial da Web. Os desenvolvedores o usam para escrever aplicativos multiplataforma que podem ser executados em qualquer plataforma e em qualquer navegador.

Embora o JavaScript seja usado para criar aplicativos multiplataforma, ele não foi concebido para aplicativos grandes envolvendo milhares ou até mesmo milhões de linhas de código. O JavaScript não tem alguns dos recursos de linguagens mais maduras presentes nos aplicativos sofisticados de hoje. Os IDEs (editores de desenvolvimento integrado) podem ter dificuldades para gerenciar o JavaScript e manter essas grandes bases de código.

O TypeScript resolve as limitações do JavaScript, fazendo isso sem comprometer a principal proposta de valor do JavaScript: a capacidade de executar seu código em qualquer lugar e em todas as plataformas, navegadores e hosts.

## **O que é o TypeScript?**

O TypeScript é uma linguagem de software livre desenvolvida pela Microsoft. Ele é um superconjunto do JavaScript, o que significa que você pode continuar a usar as habilidades de JavaScript que já desenvolveu e adicionar determinados recursos que não estavam disponíveis para você anteriormente.

### **Dicas de tipo**

O principal recurso do TypeScript é o sistema de tipos. No TypeScript, você pode identificar o tipo de dados de uma variável ou parâmetro usando uma *dica de tipo*. Com as dicas de tipo, você descreve a forma de um objeto, o que proporciona uma melhor documentação e permite que o TypeScript valide se o código está funcionando corretamente.

Por meio da verificação de tipo estático, o TypeScript detecta, no início do desenvolvimento, problemas de código que o JavaScript normalmente não consegue detectar até que o código seja executado no navegador. Os tipos também permitem que você descreva o que o seu código é destinado a fazer. Se você estiver trabalhando em uma equipe, um colega que chegue depois de você também poderá entender o código com facilidade.

Os tipos também potencializam os benefícios de inteligência e produtividade das ferramentas de desenvolvimento, como IntelliSense, navegação baseada em símbolos, ir para definição, localizar todas as referências, preenchimento de instruções e refatoração de código.

A escritura de tipos pode ser opcional no TypeScript, porque a *inferência de tipos* torna seu código muito poderoso, mesmo sem que você escreva código adicional. Se o TypeScript puder determinar o tipo de dados implicitamente (por exemplo, quando você atribuir um valor a uma variável usando `let age = 42`), ele inferirá automaticamente o tipo de dados.

### **Experimente! Aprendendo sobre tipos**

Vejamos um exemplo para demonstrar o uso de tipos.

1. Abra o [Playground](https://www.typescriptlang.org/play) do TypeScript. Você aprenderá mais sobre o Playground posteriormente neste módulo.
2. Copie e cole o seguinte exemplo de código JavaScript no painel do TypeScript (à esquerda):

    ```tsx
    function addNumbers(x, y) {
      return x + y;
    }
    
    console.log(addNumbers(3, 6));
    
    ```
    
    Observe que o mesmo código aparece no painel **.JS** (à direita). Esse é o código JavaScript que o TypeScript vai gerar depois de ser compilado.
    
3. Selecione **Executar** para executar o código JavaScript. Em seguida, selecione a guia **Logs** e observe que o valor `9` é registrado no console. O JavaScript atribuiu o tipo `number` aos parâmetros `x` e `y` e a função retornou um número.
4. Substitua `3` por `"three"` (incluindo as aspas) no código do TypeScript e execute-o. O JavaScript agora atribui o `string` tipo ao parâmetro `x` e retorna "three6", um tipo string, para o console. Você provavelmente se deparou com essa situação antes e, como você sabe, ela pode causar alguns resultados inesperados.
    
    No painel TypeScript, observe as linhas onduladas vermelhas sob os nomes de parâmetro na função `addNumbers`. Isso indica que o verificador de tipo identificou erros. Focalize um dos parâmetros e leia a descrição do erro. O TypeScript atribuiu implicitamente um tipo de `any`, que é o tipo mais amplo, pois ele basicamente pode conter qualquer coisa.
    
5. Atualize o código TypeScript para especificar um tipo para cada parâmetro. Substitua `x` por `x: number` e `y` por `y: number`.
    
    Você observará que os erros agora desapareceram dos parâmetros, mas um novo erro apareceu no primeiro argumento na chamada de função: "Um argumento de tipo 'string' não pode ser atribuído a um parâmetro de tipo 'number'."
    
6. Substitua `"three"` por um número para corrigir o erro. Você pode passar um valor literal, uma variável ou qualquer outro dado e, como o TypeScript entende a forma do seu objeto, ele pode notificá-lo do conflito de tipo durante o desenvolvimento.
7. Examine o JavaScript e observe que não há nenhuma alteração nele. O TypeScript foi capaz de fornecer a verificação de tipo durante o desenvolvimento, mas isso não teve nenhum impacto sobre o código JavaScript resultante porque ele não dá suporte a tipos.

### **Outros recursos de código do TypeScript**

O TypeScript tem recursos de codificação adicionais que você não encontrará em JavaScript:

- Interfaces
- Namespaces
- Genéricos
- Classes abstratas
- Modificadores de dados
- Opcionais
- Sobrecarga de função
- Decoradores
- Utilitários de tipo
- Palavra-chave readonly

Você aprenderá mais sobre alguns desses recursos em módulos posteriores.

## **Compatibilidade do TypeScript com o JavaScript**

O TypeScript é um superconjunto estrito do [ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/) (ECMAScript 6 ou ES6). Isso significa que todo o código JavaScript também é código TypeScript, e um programa TypeScript pode consumir o JavaScript de maneira direta.

Os navegadores entendem apenas o JavaScript. Para que seu aplicativo funcione, ao escrevê-lo em TypeScript, você precisa compilar seu código e convertê-lo em JavaScript. Você transforma o código TypeScript em código JavaScript usando o compilador TypeScript ou um transcompilador compatível com TypeScript. O JavaScript resultante é um código simples e limpo que pode ser executado em qualquer lugar em que o JavaScript é executado: em um navegador, no Node.js ou em seus aplicativos.

![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-compiler.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-compiler.png)

**Importante**

Quando você trabalha com o TypeScript, lembre-se que, em quase todas as situações, o TypeScript será compilado (ou transformado) em JavaScript e o JavaScript será realmente executado pelo runtime. Você pode usar o TypeScript em *todos* os projetos que usam JavaScript.

## **Migrar do JavaScript para o TypeScript**

Adotar o TypeScript não é uma opção binária, então você pode migrar sua base de código gradualmente. Você pode começar anotando o JavaScript existente com [JSDoc](https://jsdoc.app/) e transformando alguns arquivos para que sejam verificados pelo TypeScript. Você pode preparar a base de código ao longo do tempo para ser totalmente convertida.

Para obter mais informações sobre esse processo, confira [Tutoriais do TypeScript: migração do JavaScript](https://www.typescriptlang.org/docs/handbook/migrating-from-javascript.html).

# **Compilar um arquivo TypeScript**

Conforme você aprendeu anteriormente, o TypeScript é um superconjunto estrito do [ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/) (ECMAScript 6 ou ES6). Isso significa que todo o código JavaScript também é código TypeScript, e um programa TypeScript pode consumir o JavaScript de maneira direta. Na verdade, você pode converter um arquivo JavaScript em um arquivo TypeScript simplesmente renomeando a extensão de *.js* para *.ts*.

No entanto, nem todo código TypeScript é código JavaScript. Isso ocorre porque o TypeScript adiciona uma nova sintaxe ao JavaScript, o que torna o JavaScript mais fácil de ler e implementa alguns recursos, como a digitação estática. Embora o código TypeScript torne o desenvolvimento mais fácil e menos propenso a erros, os navegadores e a maioria dos outros runtimes não dão suporte nativo a TypeScript. Por esse motivo, o TypeScript requer uma etapa de build ([transcompilador](https://en.wikipedia.org/wiki/Source-to-source_compiler)) para transformá-lo em JavaScript para que o aplicativo funcione.

Você transforma o código TypeScript em código JavaScript usando o compilador do TypeScript ou um transcompilador compatível com TypeScript, como o [Babel](https://babeljs.io/), o [SWC](https://swc.rs/docs/installation/) ou o [sucrase](https://github.com/alangpierce/sucrase). Esse processo remove o código específico ao TypeScript (por exemplo, interfaces e declarações de tipo). Além disso, ele gera um arquivo JavaScript limpo que você pode executar em suas páginas da Web e é compatível com navegadores.

## **Compilar um arquivo TypeScript**

Você executa o compilador do TypeScript no prompt de comando usando o comando `tsc`. Quando você executa `tsc` sem parâmetros adicionais, ele compila todos os arquivos *.ts* na pasta atual e gera um arquivo *.js* para cada um deles.

Você também pode compilar um arquivo específico. Por exemplo, para compilar um arquivo TypeScript chamado *utility_functions.ts*, insira `tsc utility_functions.ts`.

**Observação**

A inserção da extensão de arquivo *.ts* é opcional.

Se não houver nenhum erro de compilador, o comando `tsc` vai gerar um arquivo JavaScript chamado *utility_functions.js*.

Se o compilador encontrar erros no código, ele os exibirá na janela Comando. Corrija os erros no arquivo TypeScript e execute o comando `tsc` novamente.

## **Opções do compilador**

Usando as opções do compilador, você pode controlar como o JavaScript é gerado do TypeScript de origem. Você pode definir as opções no prompt de comando, como faria com muitas interfaces de linha de comando ou em um arquivo JSON chamado *tsconfig.json*.

Várias opções de compilador estão disponíveis para você. Você pode encontrar uma lista completa de opções na [documentação de interfaces de linha de comando do tsc](https://www.typescriptlang.org/docs/handbook/compiler-options.html). Estas são algumas das opções mais comuns:

- `noImplicitAny`
- `noEmitOnError`
- `target`
- as opções de diretório

Para controlar a compilação, você pode usar as opções do compilador com o comando `tsc`, incluindo:

- A opção `-noImplicitAny` instrui o compilador a gerar erros em expressões e declarações com um tipo `any` implícito. Por exemplo:
    
    `tsc utility_functions.ts --noImplicitAny`
    
- A opção `-target` especifica a versão de destino do ECMAScript para o arquivo JavaScript. Este exemplo compila um arquivo JavaScript em conformidade com ECMAScript 6:
    
    `tsc utility_functions.ts --target "ES2015"`
    

Você aprenderá sobre outras opções do compilador em módulos posteriores.

# **Exercício – configurar um projeto do TypeScript**

Neste exercício, você criará um projeto do TypeScript. Em seguida, você verificará que o seu ambiente de desenvolvimento está configurado corretamente executando o compilador e verificando se o arquivo JavaScript foi gerado.

## **Configurar um projeto do TypeScript no Visual Studio Code**

Nesta etapa, você cria um workspace do projeto no Visual Studio Code e inicializa o projeto.

1. Abra o Visual Studio Code.
2. No painel de **Boas-vindas**, selecione **Adicionar pasta de workspace**.
    
    ![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-add-workspace-folder-1.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-add-workspace-folder-1.png)
    
3. Crie uma pasta de projeto e selecione **Adicionar**.
4. No painel esquerdo, selecione o botão **Explorador**.
    
    ![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-explorer-icon-2.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-explorer-icon-2.png)
    
5. No painel Explorador, selecione o ícone **Novo Arquivo**.
    
    ![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-new-file-icon-3.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-new-file-icon-3.png)
    
6. Em **Exercício do Módulo 01**, digite o nome do arquivo **module01.ts** e pressione **Enter**. O arquivo TypeScript aparece em um novo editor de código.
    
    ![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-new-typescript-file-4.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-new-typescript-file-4.png)
    

## **Gerar um arquivo tsconfig.json**

O compilador do TypeScript aplica o comportamento padrão quando você compila o código-fonte TypeScript. Mas você pode modificar as opções do compilador do TypeScript adicionando um arquivo *tsconfig.json* à raiz da sua pasta de projeto do TypeScript. Esse arquivo define as configurações do projeto TypeScript, como as opções do compilador e os arquivos que devem ser incluídos.

Você pode usar a opção `init` do compilador do TypeScript para gerar um arquivo TSConfig com as opções padrão.

1. No Visual Studio Code, abra uma nova janela Terminal selecionando **Terminal**>**Novo Terminal**.
2. No prompt de comando, digite `tsc --init`.
    
    Observe que o novo arquivo *tsconfig.json* foi adicionado ao painel Explorador. Talvez seja necessário atualizar o painel Explorador para exibir o arquivo.
    
3. Abra o arquivo *tsconfig.json* no editor de código. Você verá que ele tem muitas opções, a maioria das quais estão como comentários. Examine a descrição de cada opção habilitada.
4. No arquivo *tsconfig.json*, procure a opção de destino e altere-a para `"ES2015"`.
5. Atualize o arquivo *tsconfig.json* para que o compilador salve todos os arquivos JavaScript em uma nova pasta.
    
    a. No painel Explorador, crie uma pasta chamada *build* em seu projeto.b. No arquivo *tsconfig.json*, procure a opção `outDir`, remova o comentário e defina o parâmetro para **build**.
    
6. Salve o arquivo *tsconfig.json*.
7. No prompt de comando, digite `tsc`. Isso lê o arquivo *tsconfig.json* e redefine as opções para o projeto.

**Dica**

Para saber mais sobre o arquivo *tsconfig.json*, confira a **[Referência do TSConfig](https://www.staging-typescript.org/tsconfig)**.

## **Compilar TypeScript para JavaScript**

Vamos adicionar um código JavaScript ao arquivo TypeScript e compilá-lo.

1. Copie e cole o código JavaScript a seguir no editor **module01.ts**.
    
    
    ```tsx
    	function addNumbers(x, y) {
      return x + y;
    }
    console.log(addNumbers(3, 6));
    
    ```
    
    Observe que, embora você ainda não tenha compilado o código, o Visual Studio Code usou o suporte interno a TypeScript para verificá-lo quanto a tipos. Como antes, há erros de tipo nos dois parâmetros da função `addNumbers`.
    
    ![https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-intellisense-5.png](https://learn.microsoft.com/pt-br/training/modules/typescript-get-started/media/m01-visual-studio-code-intellisense-5.png)
    
2. Atualize o código TypeScript para especificar um tipo para cada parâmetro. Substitua `x` por `x: number` e substitua `y` por `y: number`.
3. Salve o arquivo TypeScript. O compilador do TypeScript funciona apenas na versão salva do arquivo.
4. No prompt de comando do Terminal, digite **tsc module01.ts**. O compilador deve ser executado sem erros.
    
    Observe que um novo arquivo JavaScript foi adicionado, mas não está na pasta *build* no Explorador. Talvez seja necessário atualizar o painel Explorador para exibir o arquivo. Quando você executa o comando `tsc` em apenas um arquivo, o compilador ignora o arquivo *tsconfig.json*.
    
5. Para carregar o arquivo de configuração e compilar todos os arquivos *.ts* na pasta, execute `tsc` sem nenhum nome de arquivo. Isso deve adicionar o arquivo *.js* à pasta *build*. Lembre-se de excluir o arquivo *.js* extra na pasta raiz.
6. Abra o arquivo *module01.js* e selecione o botão **Dividir o Editor à Direita** no canto superior direito para abrir um novo modo de exibição do editor.
    
    Agora, você deve ser capaz de ver os arquivos *.ts* e *.js* lado a lado. Observe que eles são idênticos, exceto pelo fato de que o arquivo *.js* não inclui as novas anotações de tipo.
    
7. No prompt de comando do Terminal, insira **node .\build\module01.js**. Isso executa o JavaScript e exibe o resultado no log do console.

## **Adicionar um arquivo HTML**

Como etapa final, adicione um arquivo HTML ao projeto para que você possa executar e testar o código JavaScript.

1. No Explorador, selecione o botão **Novo Arquivo**.
2. Digite o nome do arquivo **module01.html** e pressione **Enter**. O arquivo HTML aparece em um novo editor de código.
3. Copie e cole o HTML a seguir no editor e salve o arquivo.
    
    
    ```html
    <!DOCTYPE html>
    <html lang="en" dir="ltr">
    <head>
       <meta charset="UTF-8">
       <title>Test JavaScript</title>
    </head>
    <body>
       <h1>Test JavaScript</h1>
       <p id="date"></p>
       <p>This page calls the script module01.js and is used for testing.</p>
       <script src="./build/module01.js"></script>
    </body>
    </html>
    
    ```
    
4. No Explorador, clique com o botão direito do mouse em **module01.html** e selecione **Abrir no Navegador Padrão**.
5. Ative as ferramentas para desenvolvedores do seu navegador e você estará pronto para iniciar a codificação em TypeScript!

## **Solução do exercício**

Você pode baixar o workspace do Visual Studio Code concluído do [repositório de código do GitHub](https://github.com/MicrosoftDocs/mslearn-typescript/tree/main/code/module-01/m01-end). Para executar a solução, você precisa primeiro instalar o seguinte software em seu computador:

- Visual Studio Code (ou o IDE de sua escolha)
- npm (Gerenciador de Pacotes no Node)
- tsc (Compilador do TypeScript)

Para obter melhores resultados, siga as instruções completas para configurar seu ambiente e usar o compilador do TypeScript neste módulo. Depois de configurar o seu ambiente, execute qualquer um dos arquivos de solução ou configuração do laboratório no roteiro de aprendizagem [Criar aplicativos JavaScript usando TypeScript](https://learn.microsoft.com/pt-br/training/paths/build-javascript-applications-typescript/).

# ****Declarar tipos de variáveis em TypeScript****

O JavaScript é uma linguagem de tipo dinâmico. Embora facilite a declaração de variáveis, isso pode, em alguns casos, levar a resultados inesperados. O sistema de tipos estáticos no TypeScript permite que você descreva a forma de um objeto, fornecendo melhor documentação, e possibilita que o TypeScript valide se o seu código está funcionando corretamente. No TypeScript, declarações de namespaces, classes, propriedades, funções, variáveis e outras entidades de linguagem associam tipos a essas entidades. A maneira como um tipo é formado e associado a uma entidade de linguagem depende do tipo da entidade. Este módulo apresentará alguns dos tipos disponíveis e mostrará como associá-los a variáveis. Os módulos posteriores vão examinar como interfaces, funções e classes usam a tipagem estática.

## **Objetivos de aprendizagem**

Neste módulo, você aprenderá a:

- Explicar as vantagens das variáveis de tipo declarativo no TypeScript.
- Declarar variáveis usando tipos primitivos.
- Declarar variáveis usando tipos de objeto.
- Declarar variáveis usando tipos de união e interseção.

## ****Visão geral sobre tipos no TypeScript****

O principal benefício do TypeScript é que ele permite que você adicione tipos estáticos ao seu código JavaScript. Os tipos colocam restrições estáticas em entidades de programa, como funções, variáveis e propriedades, para que compiladores e ferramentas de desenvolvimento possam oferecer melhor verificação e assistência durante o desenvolvimento.

O sistema de tipos do tempo de compilação estático do TypeScript modela de maneira minuciosa o sistema de tipo de tempo de execução dinâmico do JavaScript, permitindo que você expresse com precisão as relações de tipo que devem existir quando os programas são executados e têm essas suposições previamente validadas pelo compilador do TypeScript. A análise de tipo do TypeScript ocorre inteiramente em tempo de compilação e não adiciona sobrecarga de tempo de execução ao programa.

Os tipos estáticos também oferecem uma forma de documentar melhor a intenção do seu código, o que ajuda você e outros desenvolvedores a entendê-lo.

[ECMAScript 2015](https://www.ecma-international.org/ecma-262/6.0/) adicionou as palavras-chave `let` e `const` para a declaração de variável em JavaScript, o que eliminou alguns dos problemas associados à palavra-chave `var` em versões anteriores. Essa alteração possibilita declarar variáveis com escopo de nível de bloco e impede que você declare a mesma variável várias vezes.

O TypeScript incentiva o uso das palavras-chave `let` e `const` para declarações de variáveis.

**Observação**

Como lembrete, a diferença entre elas é que as declarações `let` podem ser feitas sem inicialização, enquanto as declarações `const` são sempre inicializadas com um valor. E as declarações `const`, uma vez atribuídas, nunca poderão ser reatribuidas.

## **Exercício – Inferência de tipos no TypeScript**

Você pode associar tipos com variáveis por meio de anotações de tipo explícito ou por meio de inferência de tipos implícita.

Embora seja recomendado, as anotações de tipo explícitas são opcionais no TypeScript. Para fazer isso, use a sintaxe `variableName: type`. Essa instrução `let myVariable: number` declara a variável como um tipo de número sem inicializá-la. Como alternativa, você também pode inicializar a variável usando `let myVariable: number = 10`.

Para implicar o tipo de variável por meio da inferência de tipos, basta usar o mesmo formato usado no JavaScript. Por exemplo, `let myVariable = 10` infere que a variável é do tipo `number` porque ela é inicializada com o valor `10`.

Vamos abrir o [Playground](https://www.typescriptlang.org/play) e ver como isso funciona.

1. Insira as seguintes declarações de variável:
    
    ```tsx
    let x: number;   //* Explicitly declares x as a number type
    let y = 1;       //* Implicitly declares y as a number type
    let z;           //* Declares z without initializing it
    
    ```
    
2. Agora o TypeScript trata `x` como um tipo `number`. O TypeScript também infere o tipo de `y` para ser um tipo de número, pois esse é o tipo do valor usado para inicializá-la. Mas o que acontece se você tentar atribuir um tipo de valor diferente a ela? E o que acontece com a variável z?
3. Abra a guia **Erros** no Playground para monitorar se houver erros.
4. Digite `x = 1`. Isso deverá funcionar como esperado, sem erros.
5. Digite `x = "one"`. Como esperado, isso gera o erro **O tipo "string" não pode ser atribuído ao tipo "number"** porque a verificação de tipo estático não permite que um `string` seja atribuído à variável.
6. Digite `y = "one"`. Você verá que o mesmo erro é gerado. Isso ocorre porque o TypeScript inferiu que y é do tipo `number`.
7. Insira o nome da variável `y` seguido por um ponto e você observará mais uma coisa. Embora você não tenha especificado explicitamente um tipo para a variável `y`, o IntelliSense está fornecendo métodos que se aplicam somente a um tipo `number`.
8. Insira `z = 1` e `z = "one"`. O TypeScript aceitou ambos, mas por quê? Isso funciona da mesma forma que no JavaScript porque a variável `z` agora pode aceitar qualquer valor atribuído a ela. (O TypeScript inferiu que `z` é do tipo `any` porque você não atribuiu um tipo nem a inicializou quando ela foi declarada. Você aprenderá mais sobre o tipo `any` mais adiante.)

Embora seja possível inferir implicitamente tipos por meio da inferência de tipos no TypeScript, você deve fazer isso? Por meio da inferência de tipos, você obtém parte do benefício da verificação de tipo estático e do IntelliSense e isso permite que você migre gradualmente para declarações de tipo explícitas em seus projetos. Mas as declarações de tipo explícitas também fornecem uma forma de documentar melhor a intenção do seu código e fornecem um caminho mais deliberado no futuro.

## **Tipos e subtipos no TypeScript**

Antes de mergulhar no uso de tipos para declaração de variável, vamos examinar os tipos e subtipos no TypeScript.

### **Qualquer tipo**

Todos os tipos no TypeScript são subtipos de um tipo principal chamado tipo `any`. O tipo `any` é um tipo que pode representar qualquer valor de JavaScript sem restrições. Todos os outros tipos são categorizados como tipos primitivos, tipos de objeto ou parâmetros de tipo. Esses tipos apresentam várias restrições estáticas em seus valores.

![https://learn.microsoft.com/pt-br/training/modules/typescript-declare-variable-types/media/m02-types.png](https://learn.microsoft.com/pt-br/training/modules/typescript-declare-variable-types/media/m02-types.png)

### **Tipos primitivos**

Os tipos primitivos são os tipos `boolean`, `number`, `string`, `void`, `null` e `undefined` juntamente com a enumeração ou os tipos `enum` definidos pelo usuário. O tipo `void` existe apenas para indicar a ausência de um valor, como em uma função sem valor retornado. Os tipos `null` e `undefined` são subtipos de todos os outros tipos. Não é possível referenciar explicitamente os tipos nulos e indefinidos. Somente os valores desses tipos podem ser referenciados, usando os literais `null` e `undefined`.

### **Tipos de objeto e parâmetros de tipo**

Os tipos de objeto são todos os tipos de `classe`, `interface`, `matriz` e `literal (qualquer coisa que não seja um tipo primitivo).`

Tipos de classe e de interface são introduzidos por meio de declarações de classe e de interface e são referenciados pelo nome fornecido a eles em suas declarações. Tipos de classe e de interface podem ser tipos genéricos que têm um ou mais parâmetros de tipo. Você aprenderá mais sobre esses tipos de objeto em módulos posteriores.

# ****Tipos primitivos no TypeScript****

Vamos começar analisando os tipos mais básicos e comuns que você pode encontrar ao escrever código JavaScript ou TypeScript. Posteriormente, eles formarão os principais blocos de construção de tipos mais complexos.

## **Tipos boolianos**

O tipo de dados mais básico é o valor `true` ou `false`, conhecido como booliano. Por exemplo:

```tsx
let flag: boolean;
let yes = true;
let no = false;

```

## **Tipos de número e BigInteger**

Como no JavaScript, todos os números no TypeScript são valores de ponto flutuante ou BigIntegers. Esses números de ponto flutuante obtêm o tipo `number`, enquanto BigIntegers obtém o tipo `bigint`. Além de literais hexadecimais e decimais, o TypeScript também é compatível com literais binários e octais introduzidos no ECMAScript 2015. Por exemplo:

```tsx
let x: number;
let y = 0;
let z: number = 123.456;
let big: bigint = 100n;

```

## **Tipo de cadeia de caracteres**

A palavra-chave `string` representa sequências de caracteres armazenados como unidades de código UTF-16 Unicode. Como o JavaScript, o TypeScript também usa aspas duplas (`"`) ou aspas simples (`'`) para circundar dados de cadeia de caracteres.

Alguns exemplos:

TypeScriptCopiar

```tsx
let s: string;
let empty = "";
let abc = 'abc';

```

No TypeScript, você também pode usar cadeias de caracteres de modelo, que podem abranger várias linhas e ter expressões inseridas. Essas cadeias de caracteres são circundadas pelo caractere de acento grave/aspas simples ( ` ) e as expressões inseridas são no formato `${ expr }`.

Por exemplo:

TypeScriptCopiar

```tsx
let firstName: string = "Mateo";
let sentence: string = `My name is ${firstName}.
    I am new to TypeScript.`;
console.log(sentence);

```

Esse exemplo gera a saída:

ConsoleCopiar

```tsx
My name is Mateo.
    I am new to TypeScript.

```

## **Os tipos void, null e undefined**

O JavaScript e o TypeScript têm dois valores primitivos usados para sinalizar valor ausente ou não inicializado: `null` e `undefined`. Esses tipos são mais úteis no contexto das funções, portanto, vamos discuti-los mais detalhadamente em um módulo posterior.

# ****Exercício – enumerações****

Vamos explorar os diferentes tipos de dados que o TypeScript disponibiliza e o impacto que eles têm em nosso código.

## **O tipo enumerado**

Uma adição útil ao conjunto padrão de tipos de dados do JavaScript é o tipo de enumeração ou `enum`.

As enumerações oferecem um jeito fácil de trabalhar com conjuntos de constantes relacionadas. Um `enum`, é um nome simbólico para um conjunto de valores. As enumerações são tratadas como tipos de dados e você pode usá-las para criar conjuntos de constantes para uso com variáveis e propriedades.

Sempre que um procedimento aceita um conjunto limitado de variáveis, considere o uso de uma enumeração. As enumerações tornam o código mais claro e mais legível, especialmente quando são usados nomes significativos.

O uso de enumerações:

- Ajuda a reduzir erros causados pela transposição ou digitação incorreta de números.
- Torna mais fácil alterar valores no futuro.
- Torna o código mais fácil de ler, o que significa que é menos provável que os erros possam surgir nele.
- Garante a compatibilidade com o futuro. Com as enumerações, o código será menos propenso a falhar se, posteriormente, alguém alterar os valores correspondentes aos nomes dos membros.

## **Criando uma enumeração**

As enumerações permitem que você especifique uma lista de opções disponíveis. Elas são extremamente úteis quando você tem um conjunto de valores que um determinado tipo de variável pode assumir. Vamos imaginar que você tem um campo em um banco de dados externo chamado **ContractStatus**, que contém os números 1, 2 ou 3, que representam os seguintes status de contato: **Permanent**, **Temp** e **Apprentice**. Criaremos uma enumeração com esses valores e exploraremos o suporte do TypeScript.

1. Abra o [Playground](https://www.typescriptlang.org/play) e remova qualquer código existente
2. Crie um `enum` para representar nosso cenário digitando o seguinte:
    
    TypeScriptCopiar
    
    ```tsx
    enum ContractStatus {
         Permanent,
         Temp,
         Apprentice
    }
    
    ```
    
3. Agora, declare uma variável para um novo funcionário chamado `employeeStatus` do tipo `ContractStatus` e atribua `"Temp"`. Exiba o resultado no console.
    
    TypeScriptCopiar
    
    ```tsx
    let employeeStatus: ContractStatus = ContractStatus.Temp;
    console.log(employeeStatus);
    
    ```
    
4. Selecione **Executar**. Observe o valor exibido na janela **Log**. Qual valor é retornado?
5. Por padrão, os valores `enum` começam com um valor de 0, portanto, `Permanent` é 0, `Temp` é 1 e `Apprentice` é 2. Se você quiser que eles comecem com um valor diferente, neste caso 1, especifique isso na declaração `enum`. Faça as edições a seguir para que o `enum` inicie os valores em 1.
    
    
    ```tsx
    enum ContractStatus {
         Permanent = 1,
         Temp,
         Apprentice
    }
    
    ```
    
6. Execute novamente o código, selecionando **Executar**. Observe que o valor exibido agora é **2**.
7. Para exibir o nome associado à enumeração, podemos usar o indexador fornecido. Adicione o seguinte à parte inferior do código:
    
    
    ```tsx
    console.log(ContractStatus[employeeStatus]);
    
    ```
    
8. Execute o código. Observe que o valor **Temp** é exibido, que é o nome da enumeração para **Temp** ou **2**.

# **Tipos any e unknown no TypeScript**

Há ocasiões em que você precisará trabalhar com valores que são desconhecidos no momento que desenvolve seu código ou que são de um intervalo restrito de tipos de valor. Nesses casos, você pode usar os tipos `any` e `unknown` e usar a declaração de tipo e as proteções de tipo para manter o controle sobre o que o código tem permissão para fazer com os valores que são passados.

## **Qualquer tipo**

O tipo `any` é um tipo que pode representar qualquer valor de JavaScript sem restrições. Isso pode ser útil quando você está esperando um valor de uma biblioteca de terceiros ou de entradas de usuário em que o valor é dinâmico porque o tipo `any` permitirá que você reatribua diferentes tipos de valores. E, como mencionado anteriormente, o uso do tipo `any` permite que você migre gradualmente seu código JavaScript para usar tipos estáticos no TypeScript.

O seguinte exemplo declara uma variável do tipo `any` e atribui valores a ela:

```
let randomValue: any = 10;
randomValue = 'Mateo';   // OK
randomValue = true;      // OK

```

Quando este exemplo é compilado, ele não gera um erro porque o tipo `any` abrange valores de cada tipo possível. O tipo `any` recusa a verificação de tipo e não força você a fazer nenhuma verificação antes de chamar, construir ou acessar propriedades nesses valores.

O uso do tipo `any` neste exemplo permite que você chame:

- Uma propriedade que não existe para o tipo.
- `randomValue` como uma função.
- Um método que se aplica somente a um tipo `string`.

Como `randomValue` está registrado como `any`, todos os exemplos a seguir são TypeScript válidos e **não** geram um erro em tempo de compilação. No entanto, podem ocorrer erros de runtime dependendo do tipo de dados real da variável. Considerando o exemplo anterior em que `randomValue` está definido como um valor booliano, as seguintes linhas de código vão gerar problemas no runtime:

```
console.log(randomValue.name);  // Logs "undefined" to the console
randomValue();                  // Returns "randomValue is not a function" error
randomValue.toUpperCase();      // Returns "randomValue is not a function" error

```

**Importante**

Lembre-se de que toda a conveniência do `any` vem ao custo da perda da segurança de tipos. A segurança de tipos é uma das principais motivações para usar o TypeScript. Evite usar `any` quando não for necessário.

## **Tipo unknown**

Embora seja flexível, o tipo `any` pode causar erros inesperados. Para resolver isso, o TypeScript introduziu o tipo `unknown`.

O tipo `unknown` é semelhante ao tipo `any`, pois qualquer valor pode ser atribuído ao tipo `unknown`. No entanto, você não pode acessar nenhuma propriedade de um tipo `unknown`, nem os chamar ou os construir.

Este exemplo altera o tipo `any` no exemplo anterior para `unknown`. Agora, ele gerará erros de verificação de tipo e impedirá a compilação do código até que você execute a ação apropriada para resolvê-los.

```tsx
let randomValue: unknown = 10;
randomValue = true;
randomValue = 'Mateo';

console.log(randomValue.name);  // Error: Object is of type unknown
randomValue();                  // Error: Object is of type unknown
randomValue.toUpperCase();      // Error: Object is of type unknown

```

**Observação**

A principal diferença entre `any` e `unknown` é que você não pode interagir com uma variável do tipo `unknown`; fazer isso gera um erro do **compilador**. O `any` ignora qualquer verificação de tempo de compilação e o objeto é avaliado em runtime; se o método ou a propriedade existir, ele se comportará conforme o esperado.

## **Asserção de tipo**

Se você precisar tratar uma variável como um tipo de dados diferente, poderá usar uma **declaração de tipo**. Uma declaração de tipo informa ao TypeScript que você executou as verificações especiais necessárias antes de chamar a instrução. Ele informa ao compilador "confie em mim, eu sei o que estou fazendo". Uma declaração de tipo é como uma cast de tipo em outras linguagens, mas não executa nenhuma verificação especial ou reestruturação de dados. Isso não tem impacto em runtime e é usado puramente pelo compilador.

As asserções de tipo têm duas formas. Uma é a `as`-sintaxe:

`(randomValue as string).toUpperCase();`

A outra versão é a sintaxe "colchete angular":

`(<string>randomValue).toUpperCase();`

**Observação**

A `as` é a sintaxe preferida. Alguns aplicativos do TypeScript, como o JSX, podem ser confundidos ao usar o `< >` para conversões de tipo.

O exemplo a seguir executa a verificação necessária para determinar que `randomValue` é um `string` antes de usar a declaração de tipo para chamar o método `toUpperCase`.

TypeScriptCopiar

```tsx
let randomValue: unknown = 10;

randomValue = true;
randomValue = 'Mateo';

if (typeof randomValue === "string") {
    console.log((randomValue as string).toUpperCase());    //* Returns MATEO to the console.
} else {
    console.log("Error - A string was expected here.");    //* Returns an error message.
}

```

O TypeScript agora pressupõe que você tenha feito a verificação necessária. A declaração de tipo diz que `randomValue` deve ser tratado como uma `string` e o método `toUpperCase` pode ser aplicado.

## **Protetores de tipo**

O exemplo anterior demonstra o uso de `typeof` no bloco `if` para examinar o tipo de uma expressão em runtime. Isso é chamado de **proteção de tipo**.

Você pode estar familiarizado com o uso do `typeof` e `instanceof` do JavaScript para testar essas condições. O TypeScript compreende essas condições e alterará a inferência de tipos de maneira adequada quando usada em um bloco `if`.

Você pode usar as seguintes condições para saber qual é o tipo de uma variável:

| Type | Predicado |
| --- | --- |
| string | typeof s === "string" |
| number | typeof n === "number" |
| boolean | typeof b === "boolean" |
| undefined | typeof undefined === "undefined" |
| function | typeof f === "function" |
| array | Array.isArray(a) |

---

## **Unidade seguinte: Tipos de união e interseção no TypeScript**

O TypeScript oferece opções mais avançadas para declarar tipos. Os tipos de união e interseção ajudam a lidar com situações em que um tipo é composto por dois ou mais tipos possíveis, enquanto os tipos literais permitem restringir os valores atribuídos a um tipo a uma lista restrita de opções.

## **Tipos de união**

Um tipo de **união** descreve um valor que pode ser um dos vários tipos. Isso pode ser útil quando um valor não está sob seu controle (por exemplo, valores de uma biblioteca, uma API ou entrada de usuário).

O tipo `any` também pode aceitar tipos diferentes, então por que você desejaria usar um tipo de união? Os tipos de união restringem a atribuição de valores aos tipos especificados, enquanto o tipo any não tem restrições. Outro motivo é o suporte do IntelliSense.

Um tipo de união usa a barra vertical (`|`) para separar cada tipo. No seguinte exemplo, `multiType` pode ser um `number` ou um `boolean`:

TypeScriptCopiar

```tsx
let multiType: number | boolean;
multiType = 20;         //* Valid
multiType = true;       //* Valid
multiType = "twenty";   //* Invalid

```

Usando protetores de tipo, você pode trabalhar facilmente com uma variável de um tipo de união. Neste exemplo, a função `add` aceita dois valores que podem ser um `number` ou uma `string`. Se ambos os valores forem de tipos numéricos, ela os adicionará. Se ambos forem tipos de cadeia de caracteres, ela os concatenará. Caso contrário, ela gerará um erro.

TypeScriptCopiar

```tsx
function add(x: number | string, y: number | string) {
    if (typeof x === 'number' && typeof y === 'number') {
        return x + y;
    }
    if (typeof x === 'string' && typeof y === 'string') {
        return x.concat(y);
    }
    throw new Error('Parameters must be numbers or strings');
}
console.log(add('one', 'two'));  //* Returns "onetwo"
console.log(add(1, 2));          //* Returns 3
console.log(add('one', 2));      //* Returns error

```

## **Tipos de interseção**

Os tipos de interseção estão fortemente relacionados a tipos de união, mas eles são usados de maneira muito diferente. Um tipo de interseção combina dois ou mais tipos para criar um tipo que tenha **todas as propriedades** dos tipos existentes. Isso permite que você adicione tipos existentes para obter um tipo que tenha todos os recursos necessários.

Um tipo de interseção usa o e comercial (`&`) para separar cada tipo.

Os tipos de interseção são usados com mais frequência com interfaces. O exemplo a seguir define duas interfaces `Employee` e `Manager` e cria um tipo de interseção chamado `ManagementEmployee` que combina as propriedades em ambas as interfaces.

TypeScriptCopiar

```tsx
interface Employee {
  employeeID: number;
  age: number;
}
interface Manager {
  stockPlan: boolean;
}
type ManagementEmployee = Employee & Manager;
let newManager: ManagementEmployee = {
    employeeID: 12345,
    age: 34,
    stockPlan: true
};

```

Você pode aprender mais sobre interfaces no módulo [Implementar interfaces no TypeScript](https://learn.microsoft.com/pt-br/training/modules/typescript-implement-interfaces/).

## **Tipos literais**

Um literal é um subtipo mais concreto de um tipo coletivo. Isso significa que `"Hello World"` é uma `string`, mas uma `string` não é `"Hello World"` dentro do sistema de tipos.

Há três conjuntos de tipos literais disponíveis no TypeScript: `string`, `number` e `boolean`. Ao usar tipos literais, você pode especificar um valor exato que uma cadeia de caracteres, um número ou um booliano deve ter (por exemplo, "sim", "não" ou "talvez").

### **O que é a limitação literal?**

Quando você declara uma variável usando `var` ou `let` no TypeScript, está informando ao compilador que há a chance de que essa variável altere seu conteúdo. A declaração de uma variável com tipos let (por exemplo, como a `string`), permite um número infinito de valores potenciais.

Por outro lado, o uso de `const` para declarar uma variável informará ao TypeScript que esse objeto nunca será alterado. A declaração com tipos `const` para o valor (por exemplo, "Olá, Mundo").

O processo de passar de um número infinito de casos potenciais para um número menor e finito de casos em potencial é chamado de restrição.

### **Definindo tipos literais**

Os tipos literais são escritos como literais de tipo de objeto, matriz, função ou construtor e são usados para compor novos tipos com base em outros tipos.

A melhor maneira de demonstrar o uso de tipos literais é com um exemplo. Essa definição de tipo cria um tipo literal chamado `testResult`, que pode conter um dos três valores de `string`:

TypeScriptCopiar

```tsx
type testResult = "pass" | "fail" | "incomplete";
let myResult: testResult;
myResult = "incomplete";    //* Valid
myResult = "pass";          //* Valid
myResult = "failure";       //* Invalid

```

Ao definir o valor da variável `myResult`, `"incomplete"` e `"pass"` são entradas válidas, embora `"failure"` não seja um dos itens na definição do tipo `testResult`.

O TypeScript também tem tipos literais numéricos, que atuam da mesma forma que os literais de cadeia de caracteres acima. Por exemplo:

TypeScriptCopiar

```tsx
type dice = 1 | 2 | 3 | 4 | 5 | 6;
let diceRoll: dice;
diceRoll = 1;    //* Valid
diceRoll = 2;    //* Valid
diceRoll = 7;    //* Invalid

```

Você também pode usar valores `boolean` ao definir tipos literais ou qualquer combinação de tipos.

# **Tipos de coleção no TypeScript**

Os tipos de objeto são todos os tipos de classe, interface, matriz e literal (qualquer coisa que não seja um tipo primitivo). Agora, vamos examinar os tipos de matriz e de tupla.

## **Matrizes**

O TypeScript, como o JavaScript, permite que você trabalhe com matrizes. As matrizes podem ser escritas de duas maneiras. Na primeira, você usa o tipo dos elementos seguidos por colchetes (`[ ]`) para indicar uma matriz desse tipo de elemento:

TypeScriptCopiar

```tsx
let list: number[] = [1, 2, 3];

```

A segunda maneira usa um tipo `Array` genérico, usando a sintaxe `Array<type>`:

TypeScriptCopiar

```tsx
let list: Array<number> = [1, 2, 3];

```

Não há vantagem em usar uma em relação à outra, portanto, cabe a você decidir qual sintaxe usar.

## **Tuplas**

Ter uma matriz dos mesmos tipos de valor é útil, mas às vezes você tem uma matriz que contém valores de tipos mistos. Para essa finalidade, o TypeScript fornece o tipo de tupla. Para declarar uma tupla, use a sintaxe `variableName: [type, type, ...]`.

### **Exercício – tuplas**

1. Abra o [Playground](https://www.typescriptlang.org/play) e remova qualquer código existente.
2. Insira o seguinte código para criar uma tupla que contenha uma `string` e um `number`:
    
    
    ```tsx
    let person1: [string, number] = ['Marcia', 35];
    
    ```
    
3. Tente adicionar outro item à matriz. Por exemplo:
    
    
    ```tsx
    let person1: [string, number] = ['Marcia', 35, true];
    
    ```
    
4. Você verá que um erro é gerado porque os elementos na tupla `array` são fixados. A tupla `person1` é uma matriz que contém exatamente um valor `string` e um valor `numeric`.
5. Tente alternar a ordem dos itens na matriz. Por exemplo:
    
    TypeScriptCopiar
    
    ```tsx
    let person1: [string, number] = [35, 'Marcia'];
    
    ```
    
6. Você verá um erro que indica que a ordem dos valores deve corresponder à ordem dos tipos.
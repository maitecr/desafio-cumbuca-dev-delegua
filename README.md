# desafio-cumbuca-dev-delegua

Desafio técnico, promovido pela Cumbuca Dev em parceria com a Design Líquido, cujo objetivo visa o desenvolvimento de um programa para manipulação de entradas do tipo texto, fornecidas pelo usuário, em Delégua.

### Tecnologias utilizadas:
* Delégua 0.37
* Node.js 22.14
* Visual Studio Code

## Tutorial
Certifique-se de ter a lingaguem `Delégua` instalada em seu sistema.

### Instalação
Ela pode ser obtida por:
1. Instale sua extesão pelo Visual Studio Code: `https://marketplace.visualstudio.com/items?itemName=designliquido.designliquido-vscode`
2. Via comando em terminal CLI: `npm install -g delegua`
3. Verificar sua instalação ao executar, em um terminal CLI, o comando: `delegua -v` 

### Preparação
1. Clonar a aplicação em seu dispositivo através do comando: `git clone https://github.com/maitecr/desafio-login.git`
2. Abrir o projeto no Visual Studio Code

### Executar do programa
1. Abrir o arquivo `inicio.delegua`
2. À esquerda, abrir a aba "Run and Debug" e pressionar o botão de mesmo título
3. Abaixo, irá abrir um console em que o programa será executado na aba "Entrada e Saída"
4. Usuário poderá realizar a entrada de um texto e prosseguir as operações conforme for apresentado 

## Descrição
O projeto é dividido em dois diretórios e um arquivo.
**Diretórios**
* `execute`: se encontra o procedimento por onde será executado o programa;
* `util`: funções desenvolvidas para serem utilizadas no programa;
**Arquivo**
*`inicio.delegua`: arquivo que possui a chama da função para excução do programa.

### Fluxo
* O arquivo `inicio.delegue` executa função `brincando_com_texto()`, dentro do diretório `execute`, que apresenta a entrada de texto e um menu para escolha de ações no console;
* O menu apresenta 4 opções de ações a serem invocadas para o texto inserido na entrada inicial, sendo elas: (1) Total de palavras e letras, (2) Inverter frase, (3) Inverter palavras e (4) Alterar uma letra;
* O usuário fornecerá a numeração, como entrada, de acordo com a ação que deseja realizar. Para executar a ação selecionada, o código foi desenvolvido em uma estrutura "switch case".

**Opção 1 - Contagem de palavras e de letras:**
* Para contagem das palavras, foram utilizadas funções as `dividir()` e `tamanho()`, nativas do Delégua. O Delégua considera variáveis do tipo texto como um vetor, então, utilizamos a função `dividir()` indicando o espaçamento como delimitador entre valores para identificar uma palavra e, sem seguida, usamos a função `tamanho()` que retorna o número de itens existentes no vetor;
* Para a contagem de letras, foi desenvolvida uma função própria, pois a função nativa `tamanho()` retornaria todos os caracteres presentes no vetor, incluindo espaçamentos. Então, nesta função, é indicado que os espaçamentos não devem ser contabilizados.

**Opção 2 - Inverção da frase:**
* Usou-se a função nativa `inverter()` que retorna o vetor de textos com seus caracteres em ordenação contrária.

**Opção 3 - Inverção de palavras:**
* A `inverter()` reoderna os caracteres, porém tende a deixar seu conteúdo ininteligível. Visto esse cenário, foi desenvolvida a função `inverter_palavras()` que, novamente com a função nativa `dividir()`, separa as palavras no texto de entrada e, em uma estrutura de repetição, reordena as posicÕes dos itens do vetor, fazendo com que o último se torne o primeiro e sucessivamente, permitindo que a palavra, isodalamente, seja compreendida.

**Opção 4 - Alterar uma letra do texto**
* É permitido ao usuário selecionar uma letra que deseja substituir no texto informado previamente e, para tal, foram desenvolvidas as funções `checar_letra()` e `substituir_letra()`;
* Num primeiro momento, deverá ser informada qual letra se pretende alterar e será verificado se ela está presente no texto a partir da função `checar_letra()` que usa uma estrutura de repetição. A estrutura de repetição pedirá que o usuário informa a letra a ser substituída enquanto ele não informar uma letra válida;
* Após validada, será que chamada a função `substituir_letra()` que, em uma estrutura de repetição, irá identificar a posição da letra a ser substituída e será usada a função nativa `substituir()` para efetuar a troca. O texto com as substituições realizadas será atribuído a um novo vetor que será retornado com as substituiçÕes finalizadas.
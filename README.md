# <img src="https://cdn.worldvectorlogo.com/logos/c.svg" height="27"> It's a repository of C/ C++ programming 🅲🔢

<blockquote>This repository contains Full-Stack development in C/ C++ languages!</blockquote>

<div align="center"><img src="https://res.cloudinary.com/practicaldev/image/fetch/s--3u1aWUCM--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/stfvlecgmmp4dso3v0iv.jpg"></div>

# 🅲 linguagem C 🅲
<div align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/1/18/C_Programming_Language.svg" height="177"></div><br \>

Uma tarefa difícil na área de computação é convencer um estudante que aprender uma nova linguagem de programação, ou usar uma linguagem que não é a preferida dele, é necessário e essencial dentro de uma disciplina. Quando se trata de uma linguagem que para alguns está ultrapassada, como a **linguagem C**, a tarefa é ainda mais difícil.

Existem muitas razões para o aprendizado de C ser fundamental. Muitos a consideram até a "mãe de todas as linguagens de programação".

Ela foi projetada para implementar o Sistema Operacional **Unix**, ficando próxima ao sistema operacional, o que a torna uma linguagem eficiente devido ao seu hábil gerenciamento de recursos no nível do sistema.

Outro ponto importante é que essa linguagem não é limitada, mas amplamente utilizada em:

- Sistemas operacionais.
- Compiladores de linguagem.
- Drivers de rede.
- Interpretadores de linguagem.
- Áreas de desenvolvimento de utilitários de sistema.
- Sistemas embarcados (embutidos).

Outras vantagens da linguagem C, incluem:

- **Onipresente**: Qualquer que seja a plataforma, C provavelmente está disponível.
- **Portável**: Um programa em C compila com modificações mínimas em outras plataformas − às vezes até funciona de imediato.
- **Simples**: C é muito simples de aprender e praticamente não requer dependências. Basta um simples PC com o compilador e tudo está pronto para criar programas.

### Estrutura de um programa em C e processo de compilação
**C** é uma linguagem considerada de nível intermediário e precisa de um compilador para criar um código executável e para que o programa possa funcionar em uma máquina.

<blockquote><b>Compilação</b> é processo de tradução do código-fonte escrito para um código de máquina. É feita por um software especial conhecido como <b>compilador</b>, que verifica o código-fonte em busca de qualquer erro sintático ou estrutural e gera um código-objeto com extensão <code>.obj</code> (no Windows) ou <code>.o</code> (no Linux), se o código-fonte estiver livre de erros.

Iremos utilizar um compilador para o Windows, o <a href="">MinGW</a>.</blockquote>

Toda a compilação é dividida em quatro etapas:

1. **Pré-processamento**.
2. **Compilação**.
3. **Montagem (assembler)**.
4. **Vinculação (linker)**.

A figura 1 descreve todo o processo de compilação em C.

<div align="center"><img src="https://estacio.webaula.com.br/cursos/go0374/galeria/aula1/img/figura1.svg"></div>

<h5 align="center"><i>Figura 1: Processo de compilação de um programa</i></h5>

Uma **IDE**, ou **Ambiente de Desenvolvimento Integrado** (Integrated Development Environment), reúne características e ferramentas de apoio ao desenvolvimento de software com o objetivo de agilizar este processo, disponibilizando todo o processo de compilação no apertar de um botão.

### Exemplo:
Podemos detalhar o processo exemplificando a compilação em Linux de um programa em C simples como o abaixo, de nome `compilacao.c`, que escreve na tela a frase `Hello, World!`:
```c
#include <stdio.h>
int main()
{
printf("Hello World!");
    return 0;}
```
Para compilar o programa acima abre-se o prompt de comando e pressiona-se o comando abaixo:
```
gcc -save-tempscompilacao.c -o compilacao
```

A opção `-save-temps` preservará e salvará todos os arquivos temporários criados durante a compilação em **C**. Ele gerará quatro arquivos no mesmo diretório:

- compilacao.i (gerado pelo pré-processador).
- compilacao.s (gerado pelo compilador).
- compilacao.o (gerado pelo montador).
- compilacao (no Linux gerado pelo linker) ou (compilacao.exe no Windows)

Agora, entenda o papel de cada elemento do processo de compilaÇão:

### Pré-processador
O **pré-processador** é um pequeno software que aceita o arquivo-fonte C e executa as tarefas abaixo.

- Remove comentários do código-fonte.
- Faz a expansão dos arquivos de cabeçalho incluídos.
- Gera um arquivo temporário com a extensão `.i` após o pré-processamento. Ele insere o conteúdo dos arquivos de cabeçalho no arquivo de código-fonte. O arquivo gerado pelo pré-processador é maior do que o arquivo de origem original.

### Compilador
Na próxima fase da compilação C, o compilador entra em ação. Ele aceita o arquivo pré-processado temporário nome_do_arquivo.i gerado pelo pré-processador e executa as seguintes tarefas:

- Verifica o programa C para erros de sintaxe.
- Traduz o arquivo em código intermediário, ou seja, em linguagem assembly.
- Otimiza,opcionalmente, o código traduzido para melhor desempenho.
- Gera um código intermediário na linguagem assembly, após a compilação, como `nome_do_arquivo.s`. É a versão de montagem do código-fonte.

### Montador (Assembler)
Passando para a próxima fase de compilação, o **assembler** aceita o código-fonte compilado (`nome_do_arquivo.s`) e o traduz em código de máquina de baixo nível. Após a montagem bem-sucedida, gera o arquivo `nome_do_arquivo.o` (no Linux) ou `nome_do_arquivo.obj` (no Windows) conhecido como **arquivo objeto**. No nosso caso, gera o arquivo **compilacao.o**.

### Vinculador (Linker)
Finalmente, o **linker** entra em ação e executa a tarefa final do processo de compilação. Aceita o arquivo intermediário `nome_do_arquivo.o` gerado pelo assembler.

Ele liga todas as chamadas de função com sua definição original. O que significa que a função `printf ()` é vinculada à sua definição original. O **vinculador** gera o arquivo executável final.

## Variáveis e tipos de dados
Na programação, **uma variável** é **um contêiner** (área de armazenamento) para armazenar dados.

Para indicar a área de armazenamento, cada variável deve receber um nome exclusivo (identificador). Os **nomes de variáveis** são apenas a representação simbólica de um local de memória.

### Exemplo:

```c
int resultado = 95;
```

Aqui, resultado é uma variável do tipo **inteiro** (`int`). Para esta variável, é atribuído um valor inteiro, `95`.

O valor de uma variável pode ser alterado, como abaixo. Daí o nome, **variável**.

```c
char ch = 'a';

// algum código

ch = 'l';
```

## Regras para nomear uma variável
Um nome de variável pode ter letras ( A primeira letra de uma variável deve ser uma letra), dígitos e símbolo "_". 

<blockquote><b>ATENÇÃO!</b> Não há nenhuma regra sobre o tamanho que um nome de variável (identificador) pode ter. No entanto, podemos ter problemas em alguns compiladores se o nome da variável tiver mais de 31 caracteres.</blockquote>

**C** é uma linguagem fortemente tipada ou tipificada. Isso significa que o tipo da variável não pode ser alterado depois de declarado.

### Exemplo:
```c
intnumero  = 5;                                // variável inteira

numero = 5.5;                                   // erro

floatnumero ;                                    // erro
```

Aqui, o tipo de variável numérica é `int`. Você não pode atribuir um valor de **ponto flutuante** (`5.5`) a essa variável. Além disso, você não pode redefinir o tipo da variável para `float`.

<blockquote>A propósito, para armazenar valores com casas decimais em C, você precisa declarar seu tipo para <code>double</code> ou <code>float</code>.</blockquote>




# 🖥️ linguagem C++ (CPP - CPlusPlus) 🖥️
<div align="center"><img src="https://cdn.worldvectorlogo.com/logos/c.svg" height="177"></div><br \>

A linguagem **C++** é, praticamente, a mesma linguagem base da C, porém orientada a objetos (POO - OOP).

# 💻 linguagem C# (C-Sharp) 💻
<div align="center"><img src="https://iconape.com/wp-content/files/sh/51404/svg/c--4.svg" height="177"></div><br \>

Uma evolução da linguagem C++, com base em Java e Perl, se formo a linguagem **C#** (C-Sharp), uma linguagem.

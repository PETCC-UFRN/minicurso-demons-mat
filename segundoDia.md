---
layout: layoutGit
title: Minicurso de Matemática aplicada à Computação
---

<div id="sumario" class="sumario-git">
    <h1>Dia 2</h1>
   <details>
    <summary><a href="#Indução">Indução</a></summary>
      <ul>
        <li><a href="#O que é indução">O que é indução</a>
          <ul>
            <li><a href="#estrutura-da-indução">Estrutura da Indução</a></li>
          </ul>
        </li>
        <li><a href="#soma-de-gauss">Soma de Gauss</a>
          <ul>
            <li><a href="#indução-em-prática">Indução em Prática</a></li>
          </ul>
        </li>
        <li><a href="#indução-forte">Indução forte</a></li>
      </ul>
    </details>
    <details open>
    <summary><a href="#Recursão">Recursão</a></summary>
      <ul>
        <li><a href="#Onde usamos a recursão na programação">Onde usamos a recursão na programação</a>
          <ul>
            <li><a href="#recursão-vs-iteração">Recursão vs. Iteração</a></li>
          </ul>
        </li>
        <li><a href="#Perigos da recursão">Perigos da recursão</a>
          <ul>
            <li><a href="#exemplo-1-chamada-infinita-da-recursão-por-ausência-de-caso-base">Exemplo 1 -> Chamada infinita da recursão por ausência de caso base</a></li>
            <li><a href="#exemplo-2-chamada-infinita-da-recursão-por-buracos-no-caso-base">Exemplo 2 -> Chamada infinita da recursão por buracos no caso base</a></li>
            <li><a href="#exemplo-3-chamada-incompleta-por-problemas-no-passo-recursivo">Exemplo 3 -> Chamada incompleta por problemas no passo recursivo</a></li>
          </ul>
        </li>
        <li><a href="#Recursão bem definida">Recursão bem definida</a>
          <ul>
            <li><a href="#exemplo-de-recursão-bem-definida">Exemplo de recursão bem definida</a></li>
          </ul>
        </li>
        <li><a href="#Elementos básicos da recursão">Elementos básicos da recursão</a>
          <ul>
            <li><a href="#introdução-aos-elementos-básicos-da-recursão">Introdução aos elementos básicos da recursão</a></li>
          </ul>
        </li>
        <li><a href="#construindo-coleções-de-coisas">Construindo coleções de coisas</a>
          <ul>
            <li><a href="#utilizando-a-recursão-para-construir-coleções-de-coisas">Utilizando a recursão para construir coleções de coisas</a></li>
          </ul>
        </li>
        <li><a href="#Recursão em listas">Recursão em listas</a>
          <ul>
            <li><a href="#montando-construtores-de-listas">Montando construtores de listas</a></li>
            <li><a href="#descobrindo-a-função-length">Descobrindo a função LENGTH</a></li>
            <li><a href="#descobrindo-a-função-sum-exercício/desafio">Descobrindo a função SUM (Exercício/desafio)</a></li>
            <li><a href="#descobrindo-a-função-filter">Descobrindo a função FILTER</a></li>
            <li><a href="#descobrindo-a-função-map">Descobrindo a função MAP</a></li>
            <li><a href="#descobrindo-a-função-replicate">Descobrindo a função REPLICATE</a></li>
          </ul>
        </li>
        <li><a href="#Extrapolando para outros tipos">Extrapolando para outros tipos</a>
          <ul>
            <li><a href="#descobrindo-melhores-funções-even-e-odd">Descobrindo melhores funções EVEN e ODD</a></li>
            <li><a href="#verificando-se-uma-função-foi-bem-definida-recursivamente-kahoot">Verificando se uma função foi bem definida recursivamente (kahoot)</a></li>
          </ul>
        </li>
      </ul>
    </details>   <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
  </div>

# Indução
Aposto que em determinado momento, você já se deparou com algum exercício em específico que foi solicitado para resolver, seja na escola, na própria faculdade ou até mesmo em brincadeiras da internet. E de alguma forma o resolveu por naturalmente, sem utilizar nenhum artifício matemático de forma séria enquanto analisa padrões ou faz tentativa e erro. No fim, chegando a algum palpite, no qual você tem certeza que está certo. 

Dessa forma, chegada a uma conclusão, como podemos provar que uma determinada solução está certa? É aí que entra a Indução

## O que é Indução?
Indução Matemática ou Indução Finita, nada mais é que um método de demonstração. É uma forma eficaz de verificar a veracidade de uma determinada propriedade.

Imagine uma fileira de dominós, igualmente espaçados entre si, de tal forma que: derrubando um dominó, o próximo também será derrubado. 
Você concorda que nesse processo a fileira inteira de dominós será derrubada?

A Indução funciona exatamente dessa forma. Provando que uma determinada propriedade é verdade para um valor e em seguida provando que é verdade para o valor seguinte, então é verdade para todos os valores.

### Estrutura da Indução
A indução atua sobre os números inteiros não negativos (1, 2, 3, 4, 5...) e segue a seguinte estrutura:
- Passo base: Provamos que é verdade para o primeiro valor.
- Passo indutivo: Verificamos que é verdadeira para o valor seguinte.
  	- Hipótese de indução
  	- Verificação da hipótese

Por enquanto, apenas se familiarize com o que é. Ainda explicaremos como colocar em prática e sua relação com programação. 

## Analisando um problema
Há uma história, em que o matemático alemão, Carl Friedrich Gauss, recebeu como um desafio do seu professor o problema de somar todos os números de 1 até 100. O desafio na verdade era apenas uma pegadinha, que tinha o intuito de mantê-lo ocupado. Contudo, Gauss rapidamente chegou a uma resposta, sem precisar realizar o trabalho árduo de somar número após número. Com isso, vamos analisar o problema e sua solução.

Gauss percebeu algo curioso...
- A soma do primero número com o último resultava em um determinado valor
- A soma do segundo número com o penúltimo resultava no mesmo valor
- A soma do terceiro número com o antipenúltimo novamente tinha o mesmo resultado
- E assim por diante
<div style="text-align: center;">  <img src="assets/images/gauss_summation_6.png" alt=""> </div>

A partir dessas observações, vamos lentamente deduzir a fórmula que resolveria o problema de somar os números de 1 até 100.

1. Temos 100 números divididos em pares, todos com o mesmo valor:

$$
\text{Soma até 100} = 50 \cdot \text{valor de cada par}
$$

2. Cada par soma 101, pois:

$$
1 + 100 = 2 + 99 = 3 + 98 = \dots = 101
$$

Logo:

$$
\text{Soma até 100} = 50 \cdot 101
$$

3. E como $101 = 1 + 100$, podemos reescrever:

$$
\text{Soma até 100} = 50 \cdot (1 + 100)
$$

---

Agora, vamos generalizar essa ideia para qualquer número $n$:

- A quantidade de pares é $n/2$
- Cada par soma $(1 + n)$

Portanto, a fórmula geral é:

$$
\text{Soma até } n = \frac{n}{2} \cdot (1 + n)
$$
E organizando-a, temos:
$$
\text{Soma até } n = \frac{n(n + 1)}{2}
$$
Essa expressão nos dá o valor total da soma dos números inteiros de $1$ até $n$.


Contudo, isso abre a questão. Como podemos provar que essa fórmula realmente é verdade? 

### Indução em Prática
Problema: Prove que $1 + 2 + 3 + 4 + \dots + n = \frac{n(n + 1)}{2}$ é verdade para qualquer inteiro $n \geq 1$.

---

- **Passo base**  
Verificamos se isso é verdade para $n = 1$.

A fórmula nos dá:
$$
\frac{n}{2} \cdot (n + 1) = \frac{1}{2} \cdot (1 + 1) = \frac{1}{2} \cdot 2 = 1
$$

Portanto, é verdade para $n = 1$.
 
- **Passo indutivo**
(É aqui que as coisas começam a ficar um pouco mais extravagantes). 

A primeira etapa do passo indutivo é formular a Hipótese de Indução.
A nossa hipótese é a seguinte:
Suponha que a fórmula vale para algum $k \in \mathbb{N}$:

$$
1 + 2 + 3 + \dots + k = \frac{k(k + 1)}{2}
$$ 
(Perceba que isso é similar à fórmula que já vimos, porém com um k no lugar do n. O uso de variáveis diferentes ocorre porque o k representa algum número qualquer que desconhecemos, enquanto o n representa o valor que será colocado na fórmula).

Queremos provar que:
$$
1 + 2 + 3 + \dots + k + (k+1) = \frac{k + 1}{2} \cdot ((k + 1) + 1)
$$
Ou seja:
$$
1 + 2 + 3 + \dots + k + (k+1) = \frac{(k + 1)(k + 2)}{2}
$$
Como é o procedimento a partir daqui?
Vamos usar a fórmula da Hipótese de Indução como base e, a partir dela, tentar chegar à expressão que queremos provar para (k + 1), realizando operações e manipulações em uma expressão, para chegar na outra. 

Supondo que a Hipótese de Indução é verdade, sabemos que:

$$
1 + 2 + 3 + \dots + k = \frac{k(k + 1)}{2}
$$

Nosso objetivo agora é mostrar que essa fórmula também vale para (k + 1). Para isso, somamos (k + 1) dos dois lados da equação:

$$
1 + 2 + 3 + \dots + k + (k + 1) = \frac{k(k + 1)}{2} + (k+1)
$$

Colocando (k + 1) em evidência:

$$
(k + 1) \cdot \left(\frac{k}{2} + 1\right)
$$

Somando os termos dentro do parênteses:

$$
(k + 1) \cdot \left(\frac{k + 2}{2}\right)
$$

Pela comutatividade da multiplicação:

$$
\frac{(k + 1)(k + 2)}{2}
$$

Portanto, mostramos que:

$$
1 + 2 + 3 + \dots + k + (k + 1) = \frac{(k + 1)(k + 2)}{2}
$$

Ou seja. Supondo que a fórmula para k é verdade, a fórmula também é válida para (k + 1). Como mostramos que ela vale para (n = 1) (passo base) e que, se vale para (k), então vale para ( k + 1) (passo indutivo), podemos concluir por indução que:

$$
1 + 2 + 3 + \dots + n = \frac{n(n + 1)}{2}
$$

É verdadeira para todo  $n \in \mathbb{N}$:

## Exercício
Mas quando o assunto é Indução, é a prática que faz a perfeição. 
Agora chegou o seu momento, tente aplicar indução para o seguinte problema:

Prove que $n^2 > 2n$ para todo $n \geq 3$.

## Indução Forte
Mas o que acontece quando estamos analisando uma propriedade que para ser analisada ou provada, é necessário múltiplos passos? Por exemplo, tome o seguinte problema:

Suponha que a$_1$, a$_2$, a$_3$, ... é uma sequência definida da seguinte forma:
- a$_1$ = 1  
- a$_2$ = 3  
- a$_k$ = a$_{k-2}$ + 2a$_{k-1}$, para todo inteiro $k \geq 3$  

Prove que a$_n$ é ímpar para todo $n > 1$.


Perceba que a nossa fórmula é composta por uma sequência, em que um determinado termo é definido pelos dois termos anteriores. A Indução que vimos anteriormente será o suficiente para provar o problema?
Na verdade, não. Precisamos de uma ferramenta um pouco mais poderosa: a Indução Forte.
Mais tarde voltaremos para esse problema, o mantenha na cabeça por enquanto. 

### Estrutura da Indução Forte
Não se preocupe, a estrutura da Indução Forte segue a mesma linha da Indução. Ainda teremos o passo base, hipótese de indução e passo indutivo. Contudo, há algumas particularidades, o passo base pode conter prova de vários valores iniciais. Além disso, no passo indutivo, assumiremos que vários valores atráves de k são verdade, para então provar que (k+1) é verdade.

Em resumo, a estrutura da Indução Forte se dá por: 
- Passo base: Provamos que a afirmação é verdadeira para o primeiro valor (ou primeiros valores, se necessário).
- Passo indutivo: Suponhamos que a afirmação seja verdadeira para todos os valores até um certo número k .
  	- Hipótese de indução: Admitimos que a proposição vale para todos os inteiros entre o valor inicial e k.
  	- Verificação da hipótese: Usamos essa suposição para demonstrar que a proposição também é verdadeira para o valor k+1.


### Indução Forte em prática

Para ilustrar a Indução Forte em prática, tome o seguinte problema:
Seja $s_0, s_1, s_2, \dots$ uma sequência definida da seguinte forma:

$$
\begin{cases}
s_0 = 0 \\
s_1 = 4 \\
s_k = 6 s_{k-1} - 5 s_{k-2}, \quad \text{para todo inteiro } k \geq 2
\end{cases}
$$

A propriedade que queremos provar, $P(n)$, é que

$$
S_n = 5^n - 1
$$

é a fórmula fechada para um termo da sequência. Mostrando que ela é verdadeira para todos os inteiros $n \geq 0$.

---

- **Passo base**

Vamos mostrar que $P(0)$ e $P(1)$ são verdadeiros. Pela definição da sequência sabemos que:
$n = 0$ precisa resultar em 0
$n=1$ precisa resultar em 4

- Para $n = 0$:

$$
S_0 = 5^0 - 1 = 1 - 1 = 0
$$Verdade!

- Para $n = 1$:

$$
S_1 = 5^1 - 1 = 5 - 1 = 4
$$Verdade!

Os valores da fórmula realmente condizem com os valores previamente definidos.



- **Passo indutivo**

No passo indutivo, queremos mostrar que, para todos os inteiros $k \geq 1$, se $P(i)$ é verdade para todos os inteiros $i$ de $0$ até $k$, então $P(k+1)$ também é verdade.

Nossa Hipótese de Indução é a seguinte: 
Seja $k$ qualquer inteiro $k \geq 1$ e suponha que

$$
s_i = 5^i - 1 \quad \text{para todos os inteiros } i \text{ com } 0 \leq i \leq k
$$
(Perceba que agora apareceu uma nova variável, $i$. Essa variável representa um índice genérico qualquer entre 0 e $k$, e é usada para expressar que estamos assumindo que a propriedade $P(i)$ é verdadeira para todos os valores anteriores a $k+1$, ou seja, desde o início da sequência até o valor $k$.)

(Essa é a principal característica da indução forte: em vez de supor que a propriedade vale apenas para $k$, como na indução simples, aqui suponhamos que ela vale para todos os casos anteriores até k, e usamos essas informações para provar que também vale para $k+1$.)

Continuando:
Queremos mostrar que

$$
s_{k+1} = 5^{k+1} - 1
$$

é verdade.

Como $k \geq 1$, temos que $k + 1 \geq 2$, e então:

$$
\begin{aligned}
s_{k+1} &= 6 s_k - 5 s_{k-1} \quad \text{(pela definição da sequência)} \\
        &= 6 (5^k - 1) - 5 (5^{k-1} - 1) \quad \text{(pela hipótese indutiva)} \\
        &= 6 \cdot 5^k - 6 - 5 \cdot 5^{k-1} + 5 \quad \text{(realizando a multiplicação)}\\
        &= 6 \cdot 5^k - 6 - 5^{k} + 5 \quad \text{(pois } 5 \cdot 5^{k-1} = 5^k) \\
        &= 6 \cdot 5^k - 1 - 5^{k}  \quad \text{(operando -6 + 5)} \\
        &= 5^k(6 - 1) - 1 \quad \text{(colocando } 5^k \text{ em evidência)}\\
        &= 5^k \cdot 5 - 1 \quad \text{(subtraindo termos dentro do parênteses)}\\
        &= 5^{k+1} - 1 \quad \text{(pois } 5 \cdot 5^k = 5^{k+1})
\end{aligned}
$$

Provando assim que a fórmula é verdadeira!


## Exercício 
Vamos retornar àquele problema que introduzimos anteriormente, e ver se conseguimos resolvê-lo agora!

Suponha que $a_1, a_2, a_3, \ldots$ é uma sequência definida da seguinte forma:

- $a_1 = 1$  
- $a_2 = 3$  
- $a_k = a_{k-2} + 2a_{k-1}$, para todo $k \geq 3$

Prove que $a_n$ é ímpar para todo $n \geq 1$.
Dica: Na matemática definimos um número par como 2q, em que q é qualquer número inteiro. A partir disso como definimos um número ímpar?


## Indução na programação
Antes de partirmos para o próximo assunto, acredito que existem diversas discussões interessantes que podemos ter em relação à Indução. Quando utiliza-la? Quando não utiliza-la? Qual sua relação com programação? 

A Indução é especialmente útil quando estamos trabalhando problemas recursivos ou com padrões numéricos. Quando o problema em questão parece apresentar uma sequência, talvez cogitar a indução seja uma possibilidade. 
No entanto, nem todo problema exige indução. Às vezes, uma simples manipulação algébrica ou uma prova direta é suficiente. A indução pode ser desnecessária (ou até mesmo tornar a prova mais complicada) quando o caso a ser provado não depende de forma clara de casos anteriores.

Quanto à indução na programação, a relação se torna mais clara quando falamos de recursão, conceito fortemente presente na indução forte, como vimos anteriormente. Mas afinal, o que é recursão? Apesar de estar presente na indução forte, é um conceito próprio e não um sinônimo.  

# Recursão
Achou que foi por acaso que nós começamos o nosso dia aprendendo sobre indução?

Nessa seção, iremos aprender que indução e recursão são duas faces da mesma moeda, correspondendo tanto a indução a um método de prova Matemática que pode ser extrapolado para a Computação, chegando na recursão, como a recursão a uma ferramenta computacional que pode ser extrapolada para o campo das demonstrações Matemáticas, chegando-se na indução.

Da mesma forma que a indução tem sua base e passo indutivo, na recursão também teremos uma base e passo recursivo! (até os nomes se parecem, né?)

A etimologia da palavra “Recursão” remete ao latim, da palavra recursio, que significa  "corrida de volta", "retorno" ou "revolução". Ela parte do sentido de fazer de novo determinado processo, repetir um padrão ou até mesmo seguir construindo algo indefinidamente.

## Mas onde usamos a recursão na programação

Bem, como já deve ter sido percebido, a Computação está sempre se utilizando das ferramentas mais diversas para alcançar seus objetivos, sejam eles o funcionamento do sistema de uma mercearia de bairro, o cálculo da sua nota do sigaa ou garantir que você não tire a bunda da cadeira depois de abrir o TikTok.

Nesse sentido, a recursão vem na esteira daquelas ferramentas utilizadas, em termos bem simplificados, para facilitar a vida da programadora ou programador, a fim de evitar a realização manual de um trabalho repetitivo. Ontem, vimos na parte de lógica e estruturas de controle, uma ferramenta semelhante à recursão que tinha uma utilidade muito parecida com essa, vocês lembram qual era?

### Recursão vs. Iteração

<div style="text-align: center;"><img src="assets/images/boxing.jpg" alt="" style="widht:300px;height:300px;"> </div>

Isso mesmo! A iteração é uma ferramenta bem parecida com a recursão e normalmente são feitos paralelos entre as duas, sendo muitas vezes possível pensar problemas por uma perspectiva recursiva e por uma perspectiva iterativa.

Enquanto a iteração está compreendida em comandos como for, range e while, normalmente a recursão é identificada no corpo da própria função, sendo o passo base semelhante a um “ponto de parada”, e a chamada recursiva representada por um novo chamamento daquela mesma função, agora com um argumento distinto, sequencialmente.

Pode ter parecido um pouco abstrato demais por agora, mas conforme forem apresentadas as distintas aplicações, cada vez mais fará sentido o tamanho e importância das abordagens recursivas na programação. Mas, vamos lá, se eu (quase) sempre posso utilizar a iteração para resolver os meus problemas, porque eu usaria a recursão?

- Abordagem mais clara e legível para algoritmos complexos
- Deixa o código mais organizado e bem estruturado
- Especialmente útil para resolver problemas de natureza recursiva
- Especialmente útil para utilizar estruturas construídas recursivamente

Em contrapartida, a abordagem recursiva normalmente perde para a iterativa quando falamos em:

- Situações onde o foco é na eficiência/velocidade do programa
- Situações onde é necessário reduzir o consumo de memória

Ocorre que ambos esses pontos são centrais na maioria das aplicações, fazendo com que um bom programador ou uma boa programadora tenha sempre que não apenas ser capaz de diferenciar os casos onde um é mais viável que o outro, como também ser capaz de aplicar ambos de forma satisfatória.

## Perigos da recursão

Sendo assim, vejamos então alguns casos onde a recursão foi usada de forma não satisfatória…

<div style="text-align: center;"><img src="assets/images/ouroboros.jpg" alt="" style="widht:300px;height:300px;"> </div>


### Exemplo 1 -> Chamada infinita da recursão por ausência de caso base

```haskell
Loop :: Int -> Int 
Loop n = Loop (n+1)
```

### Exemplo 2 -> Chamada infinita da recursão por buracos no caso base

```haskell
LoopHole :: Int -> Int
LoopHole n
    | n == 2      = 0
    | otherwise = LoopHole (n-1)
```
(Atenção: otherwise significa “caso contrário” em inglês)

### Exemplo 3 -> Chamada incompleta por problemas no passo recursivo

```haskell
Incomplete :: Int -> Bool
Incomplete n
    | n == 1       = True
    | n == 2       = False
    | n >= 3       = Incomplete (n - 3)
    | otherwise  = Incomplete (n + 3)
```

## Recursão bem definida

Já em outros casos, a recursão pode facilitar bastante a nossa vida, garantindo soluções rápidas para problemas diversos:

### Exemplo de recursão bem definida

```haskell
IsEven :: Int -> Bool
IsEven n
    | n == 2 = True
    | n == 1 = False
    | n < 1   = IsEven (n+2)
    | n > 2   = IsEven (n-2)
``` 
(Atenção: IsEven significa “ÉPar” em inglês)

## Introdução aos elementos básicos da recursão

Nos exemplos acima, conseguimos ver com clareza os elementos centrais da recursão, quais sejam, o caso base (ou casos base) e o passo recursivo (ou passos recursivos). Também, vimos quão importante é o domínio de ambos os conceitos para garantir uma função recursiva realmente funcional!

Mas então agora já posso começar a pensar sobre como devo montar meu caso base? Devo refletir sobre quais e quantos passos recursivos minha função deve ter?

Bem, por mais que ter uma boa base de indução ajude bastante na montagem de funções recursivas, uma boa programadora ou bom programador deve ser capaz de visualizar a recursão de forma concreta antes de aplicá-la. Para isso, iremos utilizar a construção de estruturas fundamentalmente recursivas como ferramenta pedagógica para facilitar a absorção desses conceitos. 

## Utilizando a recursão para construir coleções de coisas

Uma das utilizações mais fundamentais da recursão é o seu uso para construir “coleções de coisas”, mas o que seriam essas coisas? Nesse contexto, coisas referem-se a tipos dos mais diversos, temos coleções de inteiros, de valores booleanos, de strings, de chars, de pessoas, de carros, de funções…

Por sua vez, essas coleções podem ter vários formatos, ordenações, regras, formas de interações, etc. Uma coleção aqui representa tudo aquilo que reúne coisas de determinado tipo em determinada estrutura. E, como iremos conhecer, algumas dessas coleções são fundamentalmente recursivas.

Em específico, iremos trabalhar com a coleção nomeada lista, acerca da qual conhecemos algumas características fundamentais, quais sejam: a mutabilidade dos seus elementos, a relevância de suas posições, a possibilidade de elementos repetidos, a mutabilidade do seu tamanho, e por aí vai.

Você consegue pensar de cabeça em alguma outra coleção de coisas* com regras distintas?

- Conjunto
- Par ordenado/dupla
- Bag/sacola
- Sequência
- Array
- String
- Array circular
- Tabela
- Árvore

*Estamos generalizando aqui alguns conceitos distintos no intuito de simplificar a explicação, utilizando para tal a nomenclatura de coleção de coisas, entendida como mais adequada para o fim pretendido

Ao que pensamos imediatamente quando nos vem à cabeça o nome lista, chamaremos simplificadamente de “especificação”, já à forma como iremos garantir que nossa estrutura dentro de dada linguagem se comporte como pensamos que deva se comportar uma lista, chamaremos simplificadamente de “implementação”.

Nesse momento, iremos ver uma determinada forma de implementar listas recursivamente, mas as possibilidades são amplas, desde que seja respeitada a especificação esperada desse tipo!

## Aplicação da recursão em listas

A aplicação da recursão em listas aqui parte de uma construção recursiva (quem diria?) dessa estrutura, a qual nos permite sempre acessar seus membros imediatamente anteriores, ou posteriores (a depender da escolha de implementação), facilmente, como veremos à frente.

### Montando construtores de listas

Iremos agora construir uma lista do zero, em pseudocódigo, simulando uma linguagem de programação que ainda não tenha implementado esse tipo. Para isso, precisaremos apenas de dois construtores: o caso base, que será a lista vazia, e o passo recursivo, que será a possibilidade de formar uma nova lista a partir de uma lista já existente.

Vejamos, como exemplo, a definição de uma lista de coisas x:

```haskell
Define List x :: type -> type, where
-- Aqui definimos o tipo da nossa List x
    [ ] :: List x
-- Aqui definimos o nosso caso base
    ( x : xs ) :: x -> List x -> List x
-- Aqui definimos o passo recursivo
```
Aqui, definimos um tipo recursivo que pode ser acionado de duas formas:

1) Sem qualquer exigência, podemos chamar sempre o caso base, construindo uma lista vazia com o construtor [ ].

2) Caso já tenhamos uma lista, podemos construir uma nova lista, inserindo um elemento na sua “cabeça” (perceba que poderíamos muito bem ter escolhido o “rabo” como outra opção), a partir do comando (x : xs).

Neste caso, o x pode ser qualquer coisa, vejamos sua aplicação com o tipo dos naturais:

```haskell
Define List Nat :: type where
-- Aqui definimos o tipo da nossa List Nat
    [ ] :: List Nat
-- Caso base
    ( x : xs ) :: Nat -> List Nat -> List Nat
-- Passo recursivo
```

Agora que temos em mãos os dois construtores das listas de naturais, podemos brincar um pouco, construindo listas com diferentes núermos, veja bem:

```haskell
[ ]
-- Aqui temos uma lista vazia
(1 : [ ]) = [1]
-- Aqui estamos construindo uma lista com um único elemento,
-- o número 1, ao inserirmos uma “cabeça” com o elemento
-- 1 na lista vazia.
(3 : [1,2]) = [3, 1, 2]
-- Aqui acabamos de construir uma lista com três elementos,
-- inserindo uma “cabeça” com o elemento 3 em uma lista que
-- tinha anteriormente apenas o 1 e o 2 de elementos. 
(42 : [42, 42, 42, 42]) = [42, 42, 42, 42, 42]
-- Aqui construímos uma lista com 5 elementos 42
```

Utilizando esses construtores, você consegue criar alguma outra lista?

### Descobrindo a função <span style="color: #081849; font-weight: bold;">LENGTH</span>

Agora que temos acesso a um tipo definido, por nós mesmos, recursivamente, nós podemos enfim começar a utilizar funções que se aproveitem dessa implementação!

Como primeiro exemplo, iremos definir uma função que recebe listas e retorna inteiros, representativos da quantidade de elementos dessa lista recebida. Mas nós iremos fazê-lo recursivamente!


```haskell
length :: List Int -> Int
-- O tipo da nossa função recursiva
length [ ] = 0
-- O caso base
length (x : xs) = 1 + length xs
-- O passo recursivo
```


(Atenção: length significa “comprimento” em inglês)

Olhe como foi fácil definir o caso base e o passo recursivo! Caso a lista esteja vazia, a função retorna o inteiro zero, e caso a função tenha “cabeça”, a função retorna o inteiro 1 somado ao resultado da mesma função length, chamada na lista sem essa cabeça. 

Vamos tentar desenhar no quadro para ver se dá certo mesmo?

### Descobrindo a função <span style="color: #081849; font-weight: bold;">SUM</span> (Exercício/desafio)

A partir da função length definida anteriormente, você consegue pensar como seria a construção de uma função sum (soma), definida usando uma List Nat? Vamos tentar?

<details>
    <summary >SPOILER!</summary>
<div markdown="1">
```haskell
sum :: List Int -> Int
-- O tipo da nossa função recursiva
sum [ ] = 0
-- O nosso passo base
sum (x : xs) = x + sum xs
-- O nosso passo recursivo
```

(Atenção: sum significa “soma” em inglês)

Observe que foi apenas possível fazer esta função pois já havia um tipo Int implementado na nossa linguagem de programação simulada com pseudocódigo, assim como uma operação de soma que recebe dois números do tipo Int e retorna outro Int!
</div>
</details>

Além disso, é importante explicitar o quão visível fica o entrelaçamento dos conceitos abordados utilizando-se o exemplo da função acima. Na seara da Matemática e da Indução, calcular a soma de uma quantidade n de termos em dada sequência é um exercício comum.

De forma semelhante, a função sum modificada poderia ser utilizada para calcular os n primeiros termos de uma sequência. E como é construída de forma recursiva, poderíamos utilizar a indução para provar que, assegurados o passo base e o passo indutivo, essa função nos garantiria um resultado correto todas as vezes que a chamassemos.

```haskell
sum_mod :: Nat -> List Int -> Int
sum_mod 0 xs = 0
sum_mod n [x] = sum_mod (n-1) [] + x
sum_mod n ((xs : x') : []) = sum_mod (n-1) (xs : []) + x'
-- Aqui colocamos o construtor da lista acessível
-- tanto pela cabeça como pela cauda para facilitar
-- o entendimento
sum_mod n _ = error "too small or not a sequence"
-- Caso não seja possível acessar o primeiro elemento
-- ou a lista tenha elementos insuficientes, é exibida
-- uma mensagem de erro indicando que o argumento
-- não é compatível
```

A utilização de demonstrações matemáticas para provar a corretude de uma função é algo amplamente utilizado na programação, em especial em aplicações críticas que não admitam erros. Outra possibilidade é a utilização exaustiva de casos testes e de  failsafes, mas nenhum deles garante que a aplicação não causará erros, algo que a demonstração matemática faz com 100% de certeza.

### Descobrindo a função <span style="color: #081849; font-weight: bold;">FILTER</span>

É importante perceber que não temos limitações quanto à saída das funções para utilização da recursão! Veja esse exemplo que utiliza um predicado (x -> bool) para filtrar uma lista que queremos que tenha apenas elementos que cumpram um certo critério!

```haskell
filter :: (x -> Bool) -> List x -> List x
-- O tipo da nossa função recursiva
filter p [ ] -> [ ]
-- O nosso caso base
filter p (x : xs) =
-- Agora iremos inserir uma estrutura if/then/else
	if p x
-- Caso a “cabeça” passe pelo filtro
	then (x : filter p xs)
-- Iremos acoplar ela a uma nova chamada da filter
	else filter p xs
-- Caso contrário, iremos descartar a cabeça e chamar 
-- a filter no resto ainda assim
```

Mas o que seria um predicado (x -> bool)? Nós já criamos um hoje mais cedo, lembram qual era?

<details>
    <summary >SPOILER!</summary>
<div markdown="1">

```haskell
filter :: (Int-> Bool) -> List Int -> List Int
filter p [ ] -> [ ]
filter p (x : xs) =
	if p x
	then (x : filter p xs)
	else filter p xs

filter IsEven [ ] = [ ]
filter IsEven [2, 3, 5, 65, 8, 2] = [3, 5, 65]
filter IsEven [1, 3, 3] = -- ?
```

</div>
</details>

### Descobrindo a função <span style="color: #081849; font-weight: bold;">MAP</span>
Outra função fundamental para entender a lógica da recursão é a map, que mapeia uma determinada função em todos os componentes de uma lista. Pelo nome, você conseguiria adivinhar o que ela faz?


```haskell
map :: (x -> x) -> List x -> List x
-- O tipo da nossa função recursiva
map f [ ] = [ ]
-- O nosso caso base
map f (x : xs) = (f x : map f xs)
-- O nosso passo recursivo
double :: Int -> Int
-- Aqui definimos uma função double
double n = (2n)
-- Ela recebe um inteiro, e dobra ele

map double [ ] = [ ]
map double [2, 5, 8 ] = [4, 10, 16]
map double [ 42. 43. 42] = -- ?
```

Você consegue imaginar como seria definir essa função de forma iterativa?

### Descobrindo a função <span style="color: #081849; font-weight: bold;">REPLICATE</span>
De forma semelhante, também podemos diversificar o que colocamos na entrada da nossa função! Veja só a replicate, que pega um número natural, um elemento, e o replica por essa quantidade de vezes formando uma lista!

```haskell
replicate :: Nat -> x -> List x
replicate 0 _ = [ ]
replicate n x = (x : replicate (n-1) x)

replicate 5 True = [True, True, True, True, True]
```

## É possível extrapolar para outros tipos?

Mas somente as listas são tipos recursivos? Ou então apenas as coleções de coisas são tipos recursivos? Quais outros tipos eu posso implementar recursivamente?

De forma ilustrativa, iremos apresentar uma possível implementação dos números naturais de forma recursiva, a fim de que possamos apreciar a potência da recursão. Veja como, com apenas dois construtores, podemos criar um tipo de quantidade infinita!

```haskell
define Nat :: type where
	   O :: Nat
	   S :: Nat -> Nat
```


Agora temos um tipo recursivo representante dos números naturais com dois construtores, você consegue identificar qual o caso base e qual o passo recursivo?

1) Do nada, podemos construir o zero (0)
2) Caso já tenhamos um número natural, podemos chamar o seu sucessor! (S n)

Nesse sentido, teríamos o 1 representado pelo (S 0), o 2 pelo S(S 0), o 3 pelo S(S(S 0)) e assim em diante!

### Descobrindo melhores funções <span style="color: #081849; font-weight: bold;">EVEN</span> e <span style="color: #081849; font-weight: bold;">ODD</span>

Agora que temos os naturais como tipo recursivo, podemos definir uma função ainda melhor para definir se um número é par (even), ou ímpar (odd)!

```haskell
even :: Nat -> Bool
even O = False
even (S O) = True
even (S (S n)) = even n

odd :: Nat -> Bool
odd n = even S n
```

### Verificando se uma função foi bem definida recursivamente (kahoot)


---
<script>
const dataDia2 = new Date('2025-03-11');
const agora = new Date();

if (agora < dataDia2) {
    document.body.innerHTML = '<h1 style="text-align:center; margin-top:20%;">Página Indisponível</h1>' +
                              '<p style="text-align:center;">Esta página estará disponível a partir de ' + dataDia2.toLocaleDateString() + '.</p>';
}
</script>
{% include petcccopyright.html %}

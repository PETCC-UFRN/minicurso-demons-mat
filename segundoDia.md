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
Aposto que em determinado momento, você já se deparou com algum exercício em específico que foi solicitado para resolver, seja na escola, na própria faculdade ou até mesmo em brincadeiras da internet. E de alguma forma o resolveu por dedução natural, sem utilizar nenhum artifício matemático de forma séria enquanto analisa padrões ou faz tentativa e erro. No fim, chegando a algum palpite, no qual você tem certeza que está certo. 

Dessa forma, chegada à uma conclusão, como podemos provar que uma determinada solução está certa? É aí que entra a Indução

## O que é Indução?
Indução Matemática ou Indução Finita, nada mais é que um método de demonstração. Sendo uma forma eficaz de verificar a veracidade de uma determinada propriedade.

Imagine uma fileira de dominós, igualmente espaçados entre si, de tal forma que: derrubando um dominó, o próximo também será derrubado. 
Você concorda que nesse processo a fileira inteira de dominós será derrubada?

A Indução funciona exatamente dessa forma. Provando que uma determinada propriedade é verdade para um valor e em seguida provando que é verdade para o valor seguinte, então é verdade para todos os valores.

### Estrutura da Indução
A indução atua sobre os números inteiros não negativos (1, 2, 3, 4, 5...) e segue a seguinte estrutura:
- Passo base: Provamos que é verdade para o primeiro valor.
- Passo indutivo: Provamos que é verdade para o valor seguinte.
  	- Hipótese de indução
  	- Verificação da hipótese

Por enquanto, apenas se familiarize com o que é. Ainda explicaremos como colocar em prática.

## Soma de Gauss

### Indução em Prática

## Exercício 1 

## Indução Forte

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

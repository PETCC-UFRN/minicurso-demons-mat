---
layout: layoutGit
title: Minicurso de Linux e Git
---

<div id="sumario" class="sumario-git">
    <h1>Sumário</h1>
  <details>
    <summary><a href="#expandindo-a-ideia-de-comandos">Expandindo a ideia de comandos</a></summary>
      <ul>
        <li><a href="#aliases">Aliases</a></li>
        <li><a href="#vendo-um-comando-como-arquivo">Vendo um comando como arquivo</a></li>
      </ul>
    </details>
    <details>
    <summary><a href="#instalando-programas-no-linux">Instalando programas no Linux</a></summary>
      <ul>
        <li><a href="#manualmente">Manualmente</a></li>
        <li><a href="#gerenciadores-de-pacote">Gerenciadores de pacote</a></li>
      </ul>
    </details>
    <details>
    <summary><a href="#editores-de-texto">Editores de texto</a></summary>
      <ul>
          <li><a href="#escolhendo-um-editor-de-texto">Escolhendo um editor de texto</a></li>
      </ul>
    </details>
    <details>
    <summary><a href="#Shell-scripting">Shell scripting</a></summary>
      <ul>
        <li><a href="#por-quê-Shell-scripting">Por quê Shell scripting?</a></li>
        <li><a href="#a-primeira-linha-shebang">A primeira linha: #! (shebang)</a></li>
        <li><a href="#variáveis">Variáveis</a></li>
        <li><a href="#expansões">Expansões</a></li>
        <li><a href="#condicionais">Condicionais</a></li>
        <li><a href="#operadores-lógicos-no-Shell">Operadores lógicos no Shell</a></li>
        <li><a href="#funções">Funções</a></li>
        <li><a href="#loops">Loops</a></li>
      </ul>
    </details>
    <details>
      <summary><a href="#exercícios">Exercícios</a></summary>
    </details>
  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
  </div>


# Recursão
Achou que foi por acaso que nós começamos o nosso dia aprendendo sobre indução?

Nessa seção, iremos aprender que indução e recursão são duas faces da mesma moeda, correspondendo tanto a indução a um método de prova matemática que pode ser extrapolado para a computação, chegando na recursão, como a recursão a uma ferramenta computacional que pode ser extrapolada para o campo das demonstrações matemáticas, chegando-se na indução.

Da mesma forma que a indução tem sua base e passo indutivo, na recursão também teremos uma base e passo recursivo! (até os nomes se parecem, né?)

A etimologia da palavra “Recursão” remete ao latim, da palavra recursio, que significa  "corrida de volta", "retorno" ou "revolução". Ela parte do sentido de fazer de novo determinado processo, repetir um padrão ou até mesmo seguir construindo algo indefinidamente.

## Mas onde usamos a recursão na programação

Bem, como já deve ter sido percebido, a computação está sempre se utilizando das ferramentas mais diversas para alcançar seus objetivos, sejam eles o funcionamento do sistema de uma mercearia de bairro, o cálculo da sua nota do sigaa ou garantir que você não tire a bunda da cadeira depois de abrir o TikTok.

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


### Exemplo 1 (chamada infinita da recursão por ausência de caso base)

```haskell
Loop :: Int -> Int 
Loop n = Loop (n+1)
```

### Exemplo 2 (chamada infinita da recursão por buracos no caso base)

```haskell
LoopHole :: Int -> Int
LoopHole n
    | n == 2      = 0
    | otherwise = LoopHole (n-1)
```
(Atenção: otherwise significa “caso contrário” em inglês)

### Exemplo 3 (chamada incompleta por problemas no passo recursivo)

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

Você consegue pensar de cabeça em alguma outra coleção de coisas com regras distintas?

- Conjuntos
- Duplas
- Sequências
- Árvores
- Arrays
- Strings
- Arrays circulares
- Tabelas

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

### Descobrindo a função length

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

### Descobrindo a função sum (Exercício/desafio)

A partir da função length definida anteriormente, você consegue pensar como seria a construção de uma função sum (soma), definida usando uma List Nat? Vamos tentar?

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

### Descobrindo a função filter

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

### Descobrindo a função map

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

### Descobrindo a função replicate

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

### Descobrindo melhores funções even e odd

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

# Exercícios

## Orientações sobre os exercícios

Envie os exercícios de cada dia *separados* para o email `linuxgitpetcc@gmail.com` com o assunto sempre sendo: `Dia (dia de aula) - (Nome do aluno)`

## Exercícios de Revisão da aula passada

### Exercício 1

### Exercício 2

## Exercícios da aula de hoje

### Exercício 1


### Exercício 2


### Exercício 3


### Exercício 4


### Exercício 5


### Exercício 6

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

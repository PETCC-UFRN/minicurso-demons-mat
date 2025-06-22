---
layout: layoutGit
title: Minicurso de Linux e Git
---
# Primeiros passos no Linux

<div id="sumario" class="sumario-git">
    <h1>Sumário</h1>
    <details>
        <summary><a href="#para-que-serve-a-matemática-na-computação">Para que serve a matemática na computação</a></summary>
    <ul>
        <li><a href="#a-matemática-como-berço-da-computação ">A matemática como berço da computação</a></li>
        <li><a href="#a-ponte-para-o-presente">A ponte para o presente</a></li>
    </ul>
    </details>
    <details>
            <summary><a href="#as-demonstrações-matemáticas">As demonstrações matemáticas</a></summary>
        <ul>
            <li><a href="#como-demonstramos-alguma-coisa">Como demonstramos alguma coisa</a></li>
            <li><a href="#terminologia-básica">Terminologia básica</a></li>
        </ul>
    </details>
    <details>
         <summary><a href="#exemplos-práticos">Exemplos práticos</a></summary>
        <ul>
            <li><a href="#demonstrando-a-comutatividade-da-união">Demonstrando a comutatividade da união</a></li>
        </ul>
    </details>
  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
</div>

<div style="text-align: center;"> <img alt="Meme muito engraçado sobre arquivos do sistema" src="assets/images/linux_dia1_imagem7.png" width="40%">
</div>
<br>

## Para que serve a matemática na computação?  

<cite>&mdash; "Por que preciso estudar matemática para aprender a programar?"</cite>  
<cite>&mdash; "Pra que eu vou usar matemática no mercado de trabalho?"</cite>  
<cite>&mdash; "Precisa ser bom em matemática pra ser um bom programador?"</cite>  

Essas são perguntas que você já deve ter ouvido (ou se perguntado) ao refletir sobre o papel da matemática na ciência da computação e suas áreas. A resposta é simples: **a matemática é o alicerce da tecnologia**. Ela vai além da ideia de "contas e fórmulas" do ensino médio/fundamental — seu verdadeiro papel é nos ensinar a **pensar de forma lógica, abstrata e criativa**, habilidades essenciais para resolver problemas complexos. Não é necessário ser um gênio da matemática para ser um bom programador, mas entender os conceitos e aplicações torna seu trabalho muito mais fácil e eficiente.

| >>> Seção abaixada gerada por IA, sujeita a mundanças

### A matemática como berço da computação 
A computação moderna nasceu de uma necessidade histórica de automatizar o pensamento humano. No século XIX, durante a Revolução Industrial, **Charles Babbage** projetou a **Máquina Analítica** — a primeira ideia de um computador programável. Mas foi **Ada Lovelace**, matemática e filha do poeta Lord Byron, quem deu vida ao conceito. Em 1843, ao traduzir um artigo sobre a máquina de Babbage, Lovelace acrescentou notas que mudariam a história: ela percebeu que a máquina poderia processar **símbolos além de números** (como música ou texto) se programada com algoritmos matemáticos. Seu algoritmo para calcular números de Bernoulli é considerado o **primeiro programa de computador da história**. Lovelace fez isso porque enxergava a matemática como uma **"linguagem universal"** para expressar qualquer forma de conhecimento.  

Quase 100 anos depois, em meio à Segunda Guerra Mundial, o matemático **Alan Turing** enfrentou um problema prático e urgente: decifrar os códigos da máquina **Enigma**, usada pelos nazistas para comunicações secretas. Mas seu trabalho na equipe de Bletchley Park (Reino Unido) só foi possível graças a uma revolução teórica que ele liderara anos antes. Em 1936, Turing respondeu a um desafio matemático do século XX — o **"Entscheidungsproblem"** (problema da decisão), proposto por David Hilbert — criando um modelo abstrato chamado **Máquina de Turing**. Esse dispositivo teórico, baseado em regras lógicas simples (como ler/escrever símbolos e mudar estados), provou que **qualquer problema computável** poderia ser resolvido por algoritmos. A guerra apenas acelerou a aplicação prática: Turing usou estatística e teoria da probabilidade para projetar a **"Bombe"**, máquina que automatizou a quebra da Enigma, salvando milhões de vidas.  

### A ponte para o presente  
Essa evolução mostra como crises históricas (industrialização, guerras) e mentes matemáticas se entrelaçaram:  
- Lovelace transformou **ferramentas de cálculo** em **máquinas de pensamento**;  
- Turing transformou **teoria abstrata** em **salvação prática** durante a guerra;  
- Ambos provaram que computação é **matemática em ação**.  

Hoje, quando você usa um GPS (que aplica teoria dos grafos), streaming (recomendação por álgebra linear) ou criptomoedas (criptografia de teoria dos números), está colhendo os frutos dessa jornada. Por isso, começaremos nosso curso com **lógica e demonstrações matemáticas** — não para fazer "contas", mas para você dominar a arte de **transformar abstrações em revoluções tecnológicas**.  

| >>> Fim da seção

## As demonstrações matemáticas
Uma parte fundamental do trabalho de um matemático é **provar a verdade** do que seu trabalho propõe, é para isso que servem as **demonstrações**, também chamadas de prova formal, ou simplesmente prova. Na computação, as demonstrações são muito utilizadas para provar a **corretude de algoritmos**, como veremos futuramente neste curso.

### Como demonstramos alguma coisa?
Diferente de outras ciências, na matemática não provamos coisas a partir de evidências empíricas. O que fazemos é seguir um processo lógico rigoroso, onde partindo de uma verdade (já existente) e chegamos a uma nova verdade (o que se desejava provar) a partir de transformações (como regras de inferência) que preservam a verdade. **Acho q precisa melhorar esse texto dps, mas por enquanto ta bom**

### Terminologia básica

**Proposição**: Uma afirmação que pode ser demonstrada como verdadeira ou falsa. É o bloco básico do raciocínio matemático.

**Teorema**: Uma proposição de grande importância que foi demonstrada como verdadeira.

**Lema**: Um "teorema auxiliar" - uma proposição provada que serve principalmente como passo intermediário para provar um teorema maior.

**Corolário**: Uma consequência direta de um teorema já demonstrado, que muitas vezes requer pouca ou nenhuma prova adicional.

**Conjectura**: Uma proposição que se acredita ser verdadeira, mas que ainda não foi provada (nem refutada).

**Axioma**: Uma proposição considerada evidentemente verdadeira e que serve como ponto de partida para construir teorias. Não precisa ser demonstrado.

## Exemplos práticos
Vamos ver alguns exemplos práticos de demonstrações e outros conceitos.

### Demonstrando a comutatividade da união
**Proposição**:
Para quaisquer conjuntos `(A)` e `(B)`, vale que `A U B = B U A`

**Prova Direta:**
Tome `x`, tal que `x ∈ A U B`.

Pela definição da união, temos que `x ∈ A e x ∈ B`. 

Pela comutatividade do operador lógio `e`, temos que `x ∈ B e x ∈ A`.

Novamente aplicando a definição da união, temos `x ∈ B U A`

Dessa forma, partindo da premissa `x ∈ A U B`, chegamos a `x ∈ B U A`.
| Opiniões do formato da demonstração e sugestões de outras demonstrações (mais fáceis, q não usem definições q os alunos n tem conhecimento sla) porfavor. A partir do que a gente decidir, montamos as proximas demonstrações. Tava pensando em usar uns códigos simples em python p ajudar a visualizar essas demonstrações.|

## Um breve histórico da Ciência da Computação
--- to do: uma intro melhorzinha. a criatividade nao estava fluindo !

Mas as bases da Ciência da Computação, por mais irônico que isso soe, são predecessoras dos primeiros computadores! Algoritmos existem desde a antiguidade, e eles são fundamentados em pensamentos lógicos informais: Ábacos, por exemplo, - ainda que fossem operados à mão - computavam operações como adição e subtração com base em algoritmos pré-estabelecidos. Da mesma forma, a Anticítera - um dispositivo desenvolvido pelos gregos para prever posições de corpos celestes, fases da lua e outros eventos astronômicos - é considerado o primeiro computador analógico conhecido! 

Assim, ela se estende muito além do limite físico de um computador moderno



## Matemática Discreta e Lógica na Computação

Muitas vezes, ao nos depararmos com matérias de matemática discreta e lógica, nos perguntamos onde e quando usaremos isso ao longo do nosso curso. Mas a verdade é que, desde sua origem, a computação é profundamente atrelada aos conceitos de lógica e matemática.

--- to do

A matemática discreta provides a linguagem e a matemática necessárias para entendermos e desenvolvermos sistemas computacionaus e algoritmos. Além disso, ela é fundamental para e
É comum pensar que a computação 



## Demonstrações introdutórias

Antes de qualquer coisa, é importante definirmos demonstrações: Em um contexto matemático, elas são argumentos lógicos rigorosos que provam a verdade de uma proposição, partindo de axiomas, definições, até teoremas e até previamente aceitos (veremos mais sobre esses conceitos no dia 2!). Ou seja, através de "ferramentas" que temos à nossa disposição, demonstrações são capazes de provar a veracidade (ou a não veracidade!) de hipóteses matemáticas.

Mas antes de colocarmos as nossas mãos na massa, é importante termos um norte de como demostrações de fato funcionam. Para isso, separamos 3 exemplos - todos eles de grande importância para a Computação! - que explicitam bem diferentes formas de demonstração.


> Hipótese: Os números primos são infinitos (Teorema de Euclides)

Agora, iremos provar a nossa hipótese inicial *por casos*.
***(tinha colocado contradicao, mas aparentemente nao eh considerado contradicao e o nosso mano euclides errou nisso ai)

Considere qualquer lista finita de primos p1, p2, ..., pn. Será mostrado que existe pelo menos um número primo que não está na lista.
Seja P o produto de todos os números na lista. P = p1 * p2 * ... * pn.
Seja Q = P + 1.

Então temos 2 casos:
* Q é primo. 
        Então, existe algum número primo que não está lista de primos (nesse caso, o próprio Q).
* Q não é primo.
        Então, existe algum primo p' que divide Q. Caso p' estivesse na lista, então ele dividiria ambos P e Q. Se p' divide P e Q, então pela onerigneirnge (encontrar o nome da propriedade), p' também deve dividir a diferença entre P e Q, que é (P+1)-P = 1. Já que nenhum primo divide 1, p' não pode dividir Q e P ao mesmo tempo, e, portanto, não está na lista. Então, existe algum número primo que não está lista de primos.

Isso prova que, para qualquer lista finita de números primos, existe algum número que não está na lista!

Em uma primeira análise, a infinitude dos primos pode parecer meio inútil para nós leigos. No entanto, ela é extremamente importante em uma das áreas mais cruciais da computação: a cybersegurança. Um dos sistemas de criptografia mais antigos para a transmissão segura de dados é o RSA (Rivest-Shamir-Adleman), que, de maneira breve, se baseia na criação de chaves públicas e privadas para garantir autenticidade ou segurança de dados propagados.

A sacada é: essas chaves são de fato seguras pois são geradas a partir do produto de dois números primos suficientemente grandes e distantes entre si. Para "quebrar" essa criptografia sem o conhecimento desses, a fatoração desse número é necessária - um processo que, para números muito grandes, é extremamente lento. Assim, a infinidade dos primos garante que, mesmo com avanços computacionais, existem números primos grandes o suficiente para a formação de chaves complexas o suficiente, de forma que as informações podem ser transmitidas de forma segura.



> Hipótese: A soma n² + n + 41 resulta em um número primo para todo inteiro N

--- to do: Prova por contraexemplo (maybe pedro queira fazer, ele pareceu animado com esse exemplo em especifico!)


> Hipótese: todo par maior que 2 pode ser escrito como a soma de dois primos
> ---to do: Conjectura de Goldbach; mostrar que nem sempre podemos provar que algo é verdadeiro ou nao


## Introdução a Python, Funções e Recursividade

-- to do: fazer um gancho que conecte essa à parte anterior

Para apresentar os conceitos de iteratividade e recursividade, vamos usar uma linguagem de programação que vários de vocês devem conhecer: Python! Com ela, vamos ver um pouco sobre funções, diferentes maneiras de declará-las e seus usos diversos.

### Funções

Uma função, de maneira bem bruta, é um bloco de código reutilizável que realiza uma tarefa específica. No python, podemos declarar uma função simples com a *keyword* def, seguida do nome que queremos usar e de seus argumentos. No exemplo a seguir, definimos uma função de adição simples *add*, que nos devolve a soma dos 2 números passados durante a chamada de função.

```python
def add(num1, num2):
    return num1 + num2
```
Essa função então, sempre que utilizada ao longo do cógigo de vocês, vai retornar a soma dos dois números passados:

```python
def add(num1, num2):
    return num1 + num2

print(add(4, 5))
-----------------------
9
```

Mas digamos que vocês precisem codar uma função *potencia2* que, ao receber um número b, te devolve 2 elevado a b. Como vocês fariam isso?

Bem, há várias maneiras diferentes de realizar o pedido, mas todas elas estão englobadas em 2 grandes eixos: o de abordagens iterativas e o de abordagens recursivas.

### Iteratividade Vs. Recursividade

O conceito de iteratividade, derivada da palavra "Iterativo", se refere à característica de algo que se repete ou involve repetições. Assim, uma função iterativa seria uma função que involve aquelas estruturas de repetição (também chamadas de laços ou *loops*) - o *for*, o *while*, o *do while* - que aprendemos sobre em matérias como PC ou ITP. Uma abordagem iterativa para o problema proposto há pouco é a seguinte:

```python
def potencia2_it(b):
    resultado = 1;
    for i in range(b):
        resultado *= 2
    return resultado
```
Note que, no código acima, um laço *for* é utilizado para atualizar b vezes o valor da variável _resultado_. Mas, para conseguirmos de fato definir os futuros valores dessa variável, temos que inicializá-la com o valor 1 (o elemento neutro da multiplicação!). Assim, para uma chamada de função onde b = 3, realizaríamos a operação _resultado *= 2_ 3 vezes, obtendo _resultado = 1*2*2*2 = 8_ e retornando o número 8.

Por outro lado, a definição de recursividade está atrelada à caracteristica de fazer a mesma coisa ou repetir um processo várias vezes, definindo um conceito através de uma versão simples ou anterior de si (O que, de fato, soa parecido com o conceito de iteração. Mas vamos ver que, na verdade, são bem diferentes!).

De maneira mais prática, funções recursivas são todas aquelas que "chamam a si mesmas", ou seja, definem um termo atual com base em algum anterior. Assim, elas chamam recursivamente (aha!) a si mesmas, pausando as chamadas antecedentes de forma a "buscar" termos anteriores para definir o elemento em questão.

Nesse caso, note que o resultado de uma potência de base 2 e expoente b é sempre a potência de base 2 e expoente _b-1_ multiplicado por 2. Assim, podemos escrever um termo b com base em termos anteriores:

---- colocar imagem aqui

No entanto, notamos que, ao executar o programa e chamar a seguinte função para qualquer inteiro n, o programa roda infinitamente e não retorna um resultado. 

```python
def potencia2_rec(b):
    return potencia2(b-1)*2
```

Isso ocorre porque, assim como na matemática, uma recursão precisa de *casos base* para funcionar corretamente. De fato, não temos como definir termos com base em termos anteriores sem nunca definirmos um "primeiro termo": estaríamos chamando a função referente ao número anterior sem nunca parar!

Logo, precisamos adicionar uma condição de parada referente ao primeiro termo da nossa sequência (nesse caso, o 2⁰ = 1).

```python
def potencia2_rec(b):
    if (b == 0): # caso base
        return 1
    return potencia2(b-1)*2 # chamada recursiva
```

Dessa maneira, para um b = 3, seriam feitas outras 3 chamadas recursivas antes da nossa função retornar um valor: para b = 2, b = 1 e b = 0. Note que, ao chegarmos em b = 0, o programa irá entrar na condicional de caso base que estabelecemos e retornar um valor definido. A partir daí, as chamadas anteriores são completas, e retornamos os valores de _potencia2rec(1) = potencia2rec(1) * 2 = 2_ e _potencia2rec(2) = potencia2rec(1)*2 = 4_ recursivamente, até atingirmos nossa chamada original de b = 3.

Em uma primeira exposição, a recorrência pode parecer distante da realidade e até meio "inútil". Mas alguns casos, caracterizados por uma "natureza recursiva" - ou seja, baseiam suas definições em versões anteriores de si mesmas (como a sequência de Fibonacci ou o fatorial de um número natural) - podem ser representados muito mais facilmente pela recursão! Ela torna o código mais legível e, muitas vezes, mais elegante.

Abaixo, são comparados 2 códigos - uma definição recursiva da sequência de fibonacci e uma definição iterativa.

```python
def fib(int n):
    if (n == 0)
        return 1
    if (n == 1)
        return 1
    return fib(n-1) + fib(n-2)
```

```python
def fib2(int n)
    ante = 1
    ante2 = 1
    result
    for i in range(n)
        temp = result
        result = ante + ante2
        ante2 = ante
        ante = result
    return result
```
Note que, na versão iterativa, temos que criar diversas variáveis e alterar seus valores várias vezes para mantê-las atualizadas. Por sua vez, na versão recursiva, a função estará sempre gerando esses valores de maneira recorrente, conforme à árvore representada abaixo

--- to do: gerar e colocar imagem de árvore de chamadas para fibonacci

É importante ressaltar que a versão recursiva é muitas vezes, caso não otimizada, muito mais lenta e de complexidade computacional muito mais alta do que a sua equivalente iterativa - isso ocorre porque, para cada chamada em uma recursão, são geradas todas aquelas anteriores, como ilustra a árvore acima. Isso não vai ser importante para esse minicurso, mas é interessante manter isso em mente para o futuro! Essa complexidade é de suma importância em várias áreas da computação, (e até em maratonas de programação!) onde buscamos codar funções rápidas e efetivas.


## Pincelando os Conceitos de Lógica

--- to do



## Quiz para testar o que vem pela frente!!

--- to do: fazer quiz e colocar link aqui
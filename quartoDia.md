---
layout: layoutGit
title: Minicurso de Linux e Git
---

<div id="sumario" class="sumario-git">
    <h1>Dia 4</h1>
    <summary><a href="#git-avancado">Git avançado</a></summary>
    <ul>
      <li>
        <details>
          <summary><a href="#desfazendo-alteracoes">Desfazendo alterações</a></summary>
          <ul>
            <li><a href="#desfazendo-commits-sem-ter-publicado">Desfazendo commits sem ter publicado</a></li>
          </ul>
        </details>
      </li>
      <li>
        <details>
          <summary><a href="#workflow-avancado">Workflow avançado</a></summary>
          <ul>
            <li><a href="#git-branching">Git branching</a></li>
          </ul>
        </details>
      </li>
      <li>
        <details>
          <summary><a href="#git-merging">Git merging</a></summary>
          <ul>
            <li><a href="#fast-forward-merge">Fast-forward merge</a></li>
            <li><a href="#three-way-merge">Three-way merge</a></li>
            <li><a href="#lidando-com-conflitos">Lidando com conflitos</a></li>
          </ul>
        </details>
      </li>
      <li><a href="#projeto-pt1">Projeto pt.1</a></li>
    </ul>
  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
  </div>

# Conjuntos
## Introdução

Olá a todos! Sejam bem-vindos ao quarto dia do nosso minicurso de Introdução às Demonstrações Matemáticas. Hoje iremos aprender sobre conjuntos, tanto pensando em qual a sua relação com a programação como explorando como ela faz parte do mundo das demonstrações matemáticas!
# Interseção entre Conjuntos e Programação
Bem, como já sabíamos (ou às vezes até não sabíamos ainda mas agora sabemos), tudo na matemática tradicional é descrito em função de conjuntos e seus elementos. Nesse contexto, os números naturais poderiam ser compreendidos como um subconjunto dos números inteiros, que por sua vez também poderiam ser compreendidos como um subconjunto dos números reais.

Sob essa perspectiva, as funções seriam então viagens de um conjunto de números do domínio da função para outro conjunto de números, o contradomínio. Similarmente, as operações entre números seriam operações feitas dentro dos conjuntos de números, enquanto outras representações seriam duplas ordenadas de conjuntos, como o plano, representado como um conjunto de reais no eixo x junto de um conjunto de reais no eixo y, ou um espaço, dadas as modificações necessárias.

Todavia, no mundo da computação, não são mais os seus habitantes descritos em função de conjuntos e elementos!

<div style="text-align: center;"><img src="assets/images/programacao.png" alt="" style="widht:300px;height:300px;"> </div>

### Tipos ⨯ Objetos ⨯ Conjuntos

No mundo da computação, existem várias formas de descrever os habitantes de um mundo, sendo as principais os tipos e os objetos.

<div style="text-align: center;"><img src="assets/images/coding.png" alt="" style="widht:300px;height:300px;"> </div>

No caso das linguagens de programação tipadas, cada membro do mundo é de um tipo distinto, e as funções ocorrem de tipo x -> tipo y, retornando o famigerado “type error” caso haja a tentativa inválida de operar com tipos não correspondentes àquela função, e não haja forma de coagir algum dos tipos a se adequar à tipagem esperada. Alguns tipos bastante conhecidos são o Int, o Char, a String, o Bool, etc.

Já no caso de linguagens sem tipos (que também podem ser chamados de tipo único), como a Python, todos os habitantes do mundo são objetos, e as funções ocorrem entre objetos. Por mais que possam ter uma decoração de tipos, os objetos de Python não obedecem às regras do mundo tipado.

Mas então, para onde foram os conjuntos?



## Conjuntos como inspiração para a montagem da lógica de tipos

Em primeiro momento, há de se reconhecer a utilidade de todo o arcabouço teórico matemático garantido pela teoria dos conjuntos. A noção que temos de habitantes de um mundo e de relações entre esses habitantes, o que nos garante as funções computacionais de fato, bebe primordialmente da teoria dos conjuntos!

## Conjuntos como coleções de coisas

Em segundo lugar, os conjuntos voltam a aparecer na computação, agora sob uma nova roupagem, a de coleção de coisas. Como vimos anteriormente no segundo dia, a programação se importa bastante com a possibilidade de reunir diversas coisas em uma única estrutura.

Nesse sentido, o conjunto, ou set, em inglês, destaca-se como uma estrutura que armazena informações e segue um ordenamento próprio. Assim, é fundamental diferenciar de forma mais qualificada, o que seria a especificação de um conjunto, entendido enquanto Tipo Abstrato de Dados, e o que seria uma possível implementação.

### Especificação/Tipo Abstrato de Dados

Quando falamos em especificação, normalmente nos referimos à descrição pormenorizada que o cliente ofereceu do produto/aplicação/programa que ele quer. No caso dos conjuntos, estamos nos referindo à ideia abstrata do que deveria ser um conjunto, ou seja, daquilo que se comporte da forma que esperamos que se comporte um conjunto.

Dentro da computação, chamamos de Tipo Abstrato de Dados, aqueles tipos que são conhecidos de forma abstrata enquanto regras a serem seguidas. Tudo aquilo que for implementado de forma a obedecer todas as regras esperadas pela especificação do conjunto, merecerá o nome de implementação possível de conjunto, naquele dado contexto.

### Implementação

As formas de implementar um conjunto são diversas. Várias linguagens de programação vem com o tipo/objeto set disponível em suas bibliotecas, já implementado, como é o caso de python e C++. Todavia, também nessas linguagens é possível implementar um tipo/objeto novo que respeite a especificação de conjuntos, mas com uma implementação distinta.

Por mais que pareça trabalhoso refazer algo já pronto, por vezes uma boa programadora, ou um bom programador, pode querer reimplementar algum tipo ou função dentro de uma determinada linguagem, buscando melhorar sua eficiência ou reduzir o consumo de memória, para aquela utilização específica. Já para fins pedagógicos, a implementação de Tipos Abstratos de Dados pode ser útil para explorar as diferenças entre essas possíveis implementações.

## Tipos de coleções semelhantes

Assim como os conjuntos, existem outros tipos de coleções que armazenam coisas, as quais têm regras que divergem dos conjuntos, mas que foram criadas a partir dele. Sendo assim, é essencial dominar o funcionamento de conjuntos antes de partir para estruturas mais complexas, uma vez que parte de princípios semelhantes, ainda que mais complexos.
 
Algumas coleções possíveis de serem citadas que tem estrutura que de alguma forma se assemelha a dos conjuntos são:

- Par ordenado : Composto por dois elementos ordenados, acessíveis a partir de suas posições <first,second>
- Lista finita : Composta por uma série de elementos acoplados, com início e fim
- Lista infinita : Composta por uma série de elementos acoplados, podendo ter início ou fim
- Bag/Sacola : Composta por elementos sem posição relevante, mas admitindo repetições
- Sequência : Composta por uma série de elementos acoplados e ordenados
- Dicionário : Composta por vários pares ordenados de <Chave, Valor> em que as chaves são únicas e os valores são acessados a partir de suas respectivas chaves
- Pilha : Composta por elementos acoplados, com inserção no início e remoção no fim
- Fila : Composta por elementos acoplados, com inserção no início e remoção no início

## Especificação elementar dos conjuntos

Quando falamos de conjuntos, esperamos que algumas coisas sempre aconteçam (no caso que o conjunto siga todas as regras que conhecemos da matemática). Nesse sentido, sempre é importante que esteja presente presente na especificação de um conjunto que ele:


- Possa ser construído a partir dos elementos
- Ignore elementos repetidos
- Seja capaz de dizer se alguém está dentro ou fora dele
- Possua ferramentas de inserção e remoção de elementos
- Possa estar vazio
- Informe a quantidade de seus elementos, caso finito (ou cardinalidade, caso infinito)

No caso do setI que já vem implementado no C++, encontrado na biblioteca set, são essas algumas das ferramentas que são oferecidas prontas para uso, seguindo a especificação de set:


- set( ) (x -> set (x)) : Constrói um set de elementos do tipo x
- empty( )(set -> bool) : Retorna true se o set está vazio e false se não está
- size( ) (set -> size_type) : Retorna a quantidade de elementos no set
- contains( ) (x -> set -> bool) : Retorna true se o elemento inserido como argumento está presente no set e false se não está
- emplace( ) (x -> Set -> <x , bool>) : Tenta inserir um elemento no conjunto e retorna um par ordenado com o elemento e true se foi possível inseri-lo ou com o elemento e false, se não foi possível inseri-lo 
- erase() (x-> set -> size_type) : Caso receba um elemento x como argumento, exclui o elemento da lista e retorna a quantidade de elementos removidos, podendo ser 0 ou 1.

Veja aqui um exemplo desse tipo sendo utilizado em C++:

```cpp
#include <iostream>
#include <set>

int main() {
    
    // Creating a set of integers
    std::set<int> s = {3, 5, 2, 1};
    
    for (int i = 0 ; i < s.size() ; i++)
        std::cout << x << " ";
    return 0;
}
```

### Ocasiões em que conjuntos podem aparecer

Decerto, quando se fala em estruturas de dados e em tipos abstratos de dados, sempre estaremos discutindo qual a melhor e mais adequada ferramenta para este ou aquele objetivo. No caso dos conjuntos não é diferente, assim como nos são úteis na matemática, eles também podem ser úteis na vida real durante a programação. 

Por vezes, quando se está programando não é possível decidir qual base de dados você irá utilizar. Em casos como listas de participantes com inscrições possivelmente reṕetidas, caso você queira checar se determinado participante deve ser admitido ou não, um conjunto pode ser a melhor solução. Nesse cenário seria muito custoso tratar a base de dados (eliminar as repetições), e por isso um conjunto seria um tipo ideal.

Em outros casos, como quando você quer reduzir o espaço gasto, mas não quer se preocupar com repetições, também é comum usar conjuntos, como quando se está recolhendo espaços já visitados durante o percorrimento de um labirinto,e você necessariamente terá que passar por alguns lugares mais de uma vez.

Além disso, é também na área de dados que os conjuntos e as operações envolvendo conjuntos adquirem mais relevância. Mas como este minicurso é apenas introdutório iremos nos ater ao funcionamento dos conjuntos em si, a fim de que os conceitos básicos sejam dominados para que daí possam ser compreendidos assuntos mais complexos!

### Exercício

Agora, utilizando apenas as ferramentas dispostas na especificação dos conjuntos, você seria capaz de criar um par ordenado?

<details>
    <summary>resposta: SPOILER!</summary>
    Resposta: {x, {x,y}}
</details>

## Teoria dos Conjuntos

Agora que fomos apresentados às utilidades dos conjuntos na programação, podemos utilizar a Teoria dos Conjuntos para aprofundar nosso conhecimento sobre as definições matemáticas nas quais são embasadas todas as estruturas de dados vistas anteriormente!

<div style="text-align: center;"><img src="assets/images/teoriadosconjuntos.png" alt="" style="widht:300px;height:300px;"> </div>

### Conjuntos

Na matemática, um conjunto (denotado por {}), é uma coleção de elementos de um mesmo tipo independente de ordem e da repetição de seus elementos. Vamos entender um pouco essa definição:

- Independente de ordem: Os conjuntos {1, 2, 3, 4} e {4, 3, 1, 2} são iguais por definição.

- Independente de repetição: Os conjuntos {42, 42 ,84} e {42, 84} são iguais por definição.

#### "Interface" dos conjuntos

Pela definição de um conjunto, as únicas “perguntas” que podemos fazer a ele são se um elemento de um mesmo tipo pertence ou não a ele. Como assim?

Dado o conjunto de inteiros A = {3, 5, 7, 90, 21, 42}, a única forma válida de acessar os elementos desse conjunto são pelas proposições que seguem o seguinte formato:

> Obs.: Usamos o símbolo (∈) e (∉) para denotar pertencimento e não pertencimento, respectivamente, de um elemento à um conjunto.

- 5 ∈ A&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[possui valor True]
- 42 ∉ A&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[possui valor False]
- 12 ∈ A&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[possui valor False]

Ou seja, só podemos perguntar se um elemento **do mesmo tipo dos elementos do conjunto A** pertence ou não ao conjunto.

Dessa forma, os seguintes exemplos **não** são "perguntas" válidas ao nosso conjunto A:

- Fiat uno ∈ A
- umberto ∉ A
- 43,9 ∈ A
- 4 está no indice 3 do conjunto A
- 3 aparece 2 vezes no conjunto A


#### Definindo um conjunto

Podemos definir um conjunto de várias maneiras, dentre elas:

- Citar diretamente todos os elementos do conjunto, usando chaves ({ }) : A = {1, 2, 3, 7, 5, 42}

- Definir o que significa pertencer ao conjunto: x ∈ A ≝ x tem propriedade y

- Set comprehension: A ≝ {x \| x tem propriedade y}

Vamos definir o conjunto de todas as pessoas com cabelo longo, usando dois dos métodos que acabamos de conhecer:

> L = { p \| p tem cabelo longo}

> p ∈ L ≝ p tem cabelo longo

---

##### Exercícios

Agora que aprendemos a definir conjuntos, defina os conjuntos a seguir, utilizando a notação que você mais gostou:

- Conjunto de todos os primos pares
- Conjunto de todos os ímpares, menos o 2
- Conjunto com apenas o 2
- Conjunto de conjuntos de racionais

#### Conjunto Vazio, Universo e paradoxos

Antes de partimos para entender as operações entre conjuntos, é importante conhecer os conceitos de Vazio e Universo na teoria dos conjuntos, e os possíveis problemas que podem aparecer a depender de suas definições!

<div style="text-align: center;"><img src="assets/images/dangerzone.png" alt="" style="widht:300px;height:300px;"> </div>

O conjunto vazio é, como o próprio nome diz, o conjunto que não possui elementos, ou como é mais comum de ser visto no contexto acadêmico, é o conjunto não habitado. O denotamos com o símbolo ∅.

<div style="text-align: center;"><img src="assets/images/black.png" alt="" style="widht:300px;height:300px;"> </div>

Agora, esse outro amiguinho é polêmico. Em resumo, a questão do que seria um “conjunto universal” foi um grande problema na criação da teoria dos conjuntos, já que um “conjunto que tenha tudo” é falha (Paradoxo de Russell). Então, iremos definir o conjunto universo como “o conjunto de todos os elementos em nosso escopo”, sendo essa a definição mais interessante e menos suscetível a erros. Denotaremos o conjunto universo com U (um U maiúsculo).

##### Paradoxo de Russel

Como já sabemos, podemos criar um conjunto via set-comprehension, certo? Da maneira que aprendemos, então, podemos criar o seguinte conjunto:

> P = { x \| x ∉ P}

Em palavras de rua, esse é o conjunto de todos os elementos que não pertencem a ele! Vamos pensar sobre o quão problemático isso é:

- Caso x ∉ P
- Caso x ∈ P

<div style="text-align: center;"><img src="assets/images/explosao.png" alt="" style="widht:500px;height:400px;"> </div>


Dessa forma, para evitar os paradoxos da chamada “Teoria dos Conjuntos Ingênua”, podemos melhorar nosso conceito de set comprehension e criar certas restrições:

- Um conjunto não pode se auto-referir em sua criação
- Precisamos de um “filtro” na parte esquerda do set-comprehension

> L = {p ∈ U \| p tem cabelo longo}

##### Exercícios
Vocês devem ter percebido que não definimos formalmente o conjunto vazio (∅), então, vamos fazer isso!

- Construa um conjunto sem elementos com a notação set comprehension.
- Construa **OUTRO** conjunto sem elementos com a notação set comprehension.

Responda com seu coração:
- O que seria a “igualdade” de dois conjuntos?
- Esses dois conjuntos vazios são iguais?
- L = L?

### Operações de conjuntos

Assim como temos definidas operações entre números inteiros como a soma e a multiplicação, podemos definir operações entre dois ou mais conjuntos de um mesmo tipo, vamos explorar algumas delas!

#### União

A união de dois conjuntos A e B (denotada A∪B) é a operação que combina todos os elementos distintos de ambos os conjuntos. Formalmente definimos da seguinte maneira:

<p style="text-align: center;"><strong>x ∈ A∪B ≝ x ∈ A ou x ∈ B&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ou&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A∪B ≝ {x | x ∈ A ou x ∈ B}</strong></p>

No diagrama de Venn abaixo, a área branca representa A∪B, que abranje todos os elementos de A e B:

<div style="text-align: center;"><img src="assets/images/AuniaoB.png" alt="" style="widht:300px;height:300px;"> </div>

#### Interseção 

A interseção de dois conjuntos A e B (denotada A∩B) é o conjunto formado pelos elementos que pertencem simultaneamente a A e a B. Seguindo o mesmo padrão da definição de união que vimos, complete a definição abaixo:

<p style="text-align: center;"><strong>x ∈ A∩B ≝ …&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ou&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A∩B ≝ …</strong></p>

No diagrama de Venn abaixo, a área branca representa A∩B, que abranje todos os elementos que pertencem simultaneamente a A e a B:

<div style="text-align: center;"><img src="assets/images/AinterB.png" alt="" style="widht:300px;height:300px;"> </div>

#### Diferença

A diferença entre dois conjuntos A e B (denotada por A\B ou A-B) é o conjunto dos elementos que pertencem a A mas não pertencem a B. Formalmente, temos a seguinte definição:

<p style="text-align: center;"><strong>x ∈ A\B ≝ x ∈ A e x ∉ B&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ou&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A\B ≝ {x | x ∈ A e x ∉ B}</strong></p>

No diagrama de Venn abaixo, a área branca representa A\B, mostrando a parte que pertence apenas ao conjunto A:

<div style="text-align: center;"><img src="assets/images/AforaB.png" alt="" style="widht:300px;height:300px;"> </div>

#### Complemento

O complemento de um conjunto A (denotado por Aᶜ ou A') é o conjunto de todos os elementos que não pertencem a A, considerando o universo U como referência. Formalmente, temos:

<p style="text-align: center;"><strong>Aᶜ ≝ x ∉ A&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ou&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Aᶜ ≝ {x | x ∉ A}</strong></p>

No diagrama de Venn abaixo, a área branca, externa ao círculo A, representa Aᶜ.

<div style="text-align: center;"><img src="assets/images/Acomplementar.png" alt="" style="widht:300px;height:300px;"> </div>

### Relações entre conjuntos

As relações entre conjuntos nos permitem comparar e descrever como diferentes conjuntos interagem entre si. Duas das relações mais fundamentais são a relação de inclusão (subconjunto) e a relação de igualdade, que exploraremos a seguir.

#### Contém e contido

Sendo A e B conjuntos de mesmo tipo, podemos dizer que A está contido em B quando todos os elementos de A pertencem a B. Formalmente, estabelecemos a definição da seguinte maneira:

<p style="text-align: center;"><strong>A⊆B ≝ (∀x)[x ∈ A ⇒ x ∈ B]</strong></p>


> Podemos ler da seguinte maneira: dizemos que A está contido em B (ou A é subconjunto de B) se todos os elementos de A pertencem a B

<div style="text-align: center;"><img src="assets/images/AcontidoB.png" alt="" style="widht:300px;height:300px;"> </div>

#### Igualdade

Finalmente podemos entender o que significa dois conjuntos do mesmo tipo serem iguais. A partir do conhecimento que adquirimos até aqui, podemos definir o seguinte: 

Sendo A e B conjuntos, temos:

<p style="text-align: center;"><strong>A = B ≝ A ⊆ B e B ⊆ A</strong></p>

> Se abrirmos a definição de (⊆), podemos ler da seguinte forma: A é igual a B, sse todo elemento de A pertencer à B e todo elemento de B pertencer à A.

### Demonstrações sobre conjuntos

Proposições sobre conjuntos são demonstradas ou refutadas utilizando das próprias definições, operações, e relações que vimos anteriormente. Vamos dar uma olhadinha em como se parece uma demonstração envolvendo conjuntos: 

**Sejam A, B e C conjuntos tais que  A ⊆ B e B ⊆ C, demonstre que A ⊆ C.**

Demonstração:

> Relembrando a definição de A ⊆ C, precisamos demonstrar que todo elemento de A pertence a C.

> Temos que todo elemento de A pertence a B, visto que A ⊆ B.

> Temos que todo elemento de B pertence a C, visto que B ⊆ C.

> Como todos os elementos de A pertencem a B, e todos os elementos de B pertencem a C, então todos os elementos de A pertencem a C.

---

##### Exercícios

Seguindo a mesma idéia da demonstração que acabamos de ver, demonstre as seguintes proposições:

> Considere A, B e C conjuntos do mesmo tipo.

- Se A = B e B ⊆ C , então A ⊆ C.
- A ⊆ A ∪ B
- A ⊈ B\A
- Se A ⊆ B & x ∈ A, então x ∈ B

> Nota: sinta-se livre para pedir ajuda caso não consiga prosseguir com alguma demonstração!

### list/set comprehension na programação

Algumas aplicações interessantes dessa noção ocorrem em linguagens como Python, haskell, C# (com extensão), entre outras. Hoje iremos ver sua aplicação em Python.

#### List ⨯ Set

<div style="text-align: center;"><img src="assets/images/versus.png" alt="" style="widht:300px;height:300px;"> </div>

Como visto anteriormente nesse dia, vocês viram que existem algumas estruturas de dados similares aos conjuntos, também viram que as Listas são um exemplo disso.
Ao contrário de conjuntos, as listas possuem algumas propriedades específicas que tornam ela “especial”, sendo algumas delas:

- Ordem
- Acesso direto por índice
- Possibilidade de duplicatas

Apenas olhando dessa forma, vem a pergunta: Então por que utilizamos conjuntos?
A resposta não é tão simples, pois, o motivo de usar alguma estrutura de dados é variável. Porém, os maiores “defeitos” dos conjuntos se tornam sua “maior virtude”, visto que, o uso de conjuntos tem as seguintes vantagens:

- Elementos únicos.
- Bem otimizado.
- Filtragem eficiente.

Sendo assim, temos os seguintes casos para cada estrutura:

List:
- Ordem importa
- Possibilidade de elementos repetidos
- Precisa acessar elementos por índice

uso comum:
-Histórico
-Sequência de dados

Sets:
- Ordem não importa
- Elementos únicos
- Eficiência na busca

uso comum:
- “Limpar” listas com possíveis duplicatas
- Contagem de itens distintos.

#### Set/List Comprehension em si
Vamos supor que você tenha uma lista com alguns números e seu chefe tenha solicitado para que você separe cada número ímpar e forme outra lista com o dobro de cada um deles. Bem idiota, não? Provavelmente, o normal seria fazer da seguinte forma:

```python
numeros = [1, 2, 3, 4, 42, 21, 5]
trabalho_chato = []

for n in numeros:
	if n % 2 == 1:
		trabalho_chato.append(2 * n)
print(trabalho_chato)
```

Isso definitivamente não é a forma mais “elegante” de se escrever esse código. O uso de list comprehension é para “simplificar” e deixar o código mais legível, de forma onde não temos que fazer esse loop para gerar uma lista. Por exemplo, podemos alterar esse código para:

```python
numeros = [1, 2, 3, 4, 42, 21, 5]
trabalho_legal = [2 * n for n in numeros if n % 2 == 1]
print(trabalho_legal)
```
Note que, é MUITO similar ao que estamos acostumados em conjuntos (no “papel”), já que segue a forma “” elemento -> condição "".
Na prática não tem diferença entre os dois códigos, porém, note que o de baixo está mais compacto e legível.
Para utilizar esse conceito em Sets não é tão diferente (obs: pode variar dependendo da linguagem, mas a lógica se mantém), em python por exemplo, a única diferença é que ao invés dos colchetes ([]) utilizamos chaves ({}).
Vantagens da sintaxe:
- O código fica menor
- O código fica mais legível para terceiros
- Geralmente é mais eficiente do que o “jeito normal”



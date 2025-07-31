---
layout: layoutGit
title: Minicurso de Linux e Git
---

<div id="sumario" class="sumario-git">
    <h1>Dia 4</h1>
    <details>
        <summary><a href="#teoria-dos-conjuntos">Teoria dos Conjuntos</a></summary>
        <ul>
            <li><a href="#conjuntos">Conjuntos</a>
              <ul> 
                  <li><a href='#"interface"-dos-conjuntos'>"Interface" dos conjuntos</a></li>
                  <li><a href='#definindo-um-conjunto'>Definindo um conjunto</a></li>
                  <li><a href='#conjunto-vazio'>Conjunto Vazio</a></li>
                  <li><a href='#conjunto-universo'>Conjunto Universo</a></li>
                  <li><a href='#paradoxo-de-russell'>Paradoxo de Russell</a></li>
              </ul>
            </li>
            <li><a href="#operações-de-conjuntos">Operações de Conjuntos</a>
              <ul> 
                  <li><a href='#união'>União</a></li>
                  <li><a href='#interseção'>Interseção</a></li>
                  <li><a href='#diferença'>Diferença</a></li>
                  <li><a href='#complemento'>Complementoo</a></li>
              </ul>
            </li>
            <li><a href="#relações-entre-conjuntos">Relações entre Conjuntos</a>
              <ul> 
                  <li><a href='#contém-e-contido'>Contém e Contido</a></li>
                  <li><a href='#igualdade'>Igualdade</a></li>
              </ul>
            </li>
            <li><a href="#demonstrações-sobre-conjuntos">Demonstrações sobre Conjuntos</a></li>
        </ul>
    </details>
  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
</div>

# Interseção entre Conjuntos e Programação

Olá a todos! Sejam bem-vindos ao quarto dia do nosso minicurso de Matemática aplicada à Programação. Hoje iremos aprender sobre conjuntos, tanto pensando na sua definição matemática como explorando a sua relação com a programação! 

## Teoria dos Conjuntos

Antes de vermos as aplicações de conjuntos na Computação, precisamos entender quais as especificações, ou seja, as definições, propriedades e relações, que caracterizam um conjunto na Matemática.

<div style="text-align: center;"><img src="assets/images/teoriadosconjuntos.png" alt="" style="widht:300px;height:300px;"> </div>

### Conjuntos

Na Matemática, um conjunto (denotado por {}), é uma coleção de elementos de um mesmo tipo independente de ordem e da repetição de seus elementos. Vamos entender um pouco essa definição:

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
- Conjunto com apenas o 42
- Conjunto de conjuntos de racionais

#### Conjunto Vazio

O conjunto vazio (representado pelo símbolo ∅, ou {}) é o conjunto que não possui elementos.  De maneira mais formal, temos: (∀x)[ x ∉ Ø ]. Lê-se “para todo x, x não pertence ao conjunto vazio”. Assim como qualquer outro conjunto, temos diversas maneiras de defini-lo, isso será um exercício mais para frente!

<div style="text-align: center;"><img src="assets/images/black.png" alt="" style="widht:300px;height:300px;"> </div>

#### Conjunto Universo

Para evitarmos alguns paradoxos e contradições, não vamos pensar no Universo como “o conjunto que possui todos os conjuntos” ou “o conjunto que possui todos os elementos”, mas sim como “o conjunto que possui todos os elementos **do nosso escopo**”. Vamos ver alguns exemplos:

> se estamos falando de pessoas, podemos definir o universo como o conjunto de todas as pessoas.

> se estamos falando de números naturais, podemos definir o universo como o conjunto de todos os números naturais.


#### Paradoxo de Russell

Como dito anteriormente, definições mal pensadas podem nos levar a paradoxos e contradições. Vamos ver o nosso primeiro exemplo disso na prática! 

<div style="text-align: center;"><img src="assets/images/dangerzone.png" alt="" style="widht:300px;height:300px;"> </div>

Como já sabemos, podemos criar um conjunto via set-comprehension, certo? Da maneira que aprendemos, então, podemos criar o seguinte conjunto:

> P = { x \| x ∉ P}

Em palavras de rua, esse é um conjunto de todos os elementos que não pertencem a ele! Para começarmos a compreender o quão problemática essa definição pode ser, podemos separar em casos a partir de um elemento x no nosso escopo:

- Caso x ∉ P, então x ∈ P. \| **CONTRADIÇÃO!**
- Caso x ∈ P, então x ∉ P. \| **CONTRADIÇÃO!**


<div style="text-align: center;"><img src="assets/images/explosao.png" alt="" style="widht:500px;height:400px;"> </div>


Dessa forma para evitar os paradoxos da chamada “Teoria dos Conjuntos Ingênua”, podemos melhorar o nosso conceito de set comprehension e criar certas restrições:

- Um conjunto não pode se auto-referir em sua criação
- Precisamos de um “filtro” na parte esquerda do set-comprehension
- Esse filtro precisa ser um conjunto

> L = {p ∈ P \| p tem cabelo longo}


##### Exercícios

Agora que sabemos o que significa ser conjunto Vazio, construa dois conjuntos vazios de **duas maneiras diferentes**,
utilizando a notação de definir conjuntos de sua preferência!

A partir do conhecimento que temos, chute:
- O que seria a “igualdade” de dois conjuntos?
- Esses dois conjuntos vazios são iguais?
- L = L? (as duas maneiras que definimos L na seção "Definindo um conjunto")

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

## Conjuntos e Programação
Bem, como já sabíamos (ou às vezes até não sabíamos ainda mas agora sabemos), tudo (ou quase tudo) na Matemática tradicional é descrito em função de conjuntos e seus elementos. Nesse contexto, os números naturais poderiam ser compreendidos como um subconjunto dos números inteiros, que por sua vez também poderiam ser compreendidos como um subconjunto dos números reais.

Sob essa perspectiva, as funções seriam então viagens de um conjunto de números do domínio da função para outro conjunto de números, o contradomínio. Similarmente, as operações entre números seriam operações feitas dentro dos conjuntos de números, enquanto outras representações seriam duplas ordenadas de conjuntos, como o plano, representado como um conjunto de reais no eixo x junto de um conjunto de reais no eixo y, ou um espaço, dadas as modificações necessárias.

Todavia, no mundo da Computação, não são mais os seus habitantes descritos em função de conjuntos e elementos!

(Fun fact: Na Matemática, é chamado de teoria das categorias o campo teórico em que estudamos os diferentes mundos a partir de seus habitantes e das viagens entre eles)

<div style="text-align: center;"><img src="assets/images/programacao.png" alt="" style="widht:300px;height:300px;"> </div>

### Tipos ⨯ Objetos ⨯ Conjuntos/Sets

No mundo da Computação, existem várias formas de descrever os habitantes de um mundo, sendo as principais os tipos e os objetos.

<div style="text-align: center;"><img src="assets/images/coding.png" alt="" style="widht:300px;height:300px;"> </div>

Aqui, é importante fazer uma diferenciação de conceitos que se sobrepõem de forma não ignorável! Ocorre que tanto no mundo da Matemática com no mundo da Computação temos tanto tipos como conjuntos, de forma que seria impossível, ou no mínimo imprudente, seguir adiante sem fazer as devidas distinções.

Conjuntos, no mundo da Matemática, referem-se ao que acabamos de ver no tópico anterior, sendo parte componente das bases da matemática tradicional. Tipos, no mundo da matemática, por sua vez, representam uma outra possível diferenciação dos habitantes desse mundo, utilizada na Teoria dos Tipos, e fundamental para garantir uma ponte teórica sólida entre matemática e computação, em especial na esfera axiomática. Todavia, os tipos da teoria dos tipos não estarão sendo abordados no presente minicurso, em razão de sua complexidade teórica e do curso tempo disponível.

Já no mundo da programação, Conjuntos são considerados como um possível tipo, representando uma coleção de coisas, sendo a isso somadas a uma série de regras de utilização e operações. Por conta disso, desse ponto em diante, quando estivermos falando do ponto de vista da Computação, chamaremos conjuntos de Sets (correspondente a tradução de conjuntos para a língua inglesa), a fim de garantir uma fcil diferenciação.

Da mesma forma, também os tipos na programação terão um significado distinto, tendo se escolhido, entretanto, manter a nomenclatura original deste. Sendo assim, daqui em diante, sempre que aparecer o nome tipo, será em razão de estarmos falando da perspectiva computacional. Nesse dentido, no mundod da Computação, tipos será muitas vezes o nome dado aos habitantes do mundo.

No caso das linguagens de programação tipadas, cada membro do mundo é de um tipo distinto, e as funções ocorrem de tipo x para tipo y, retornando-se o famigerado “type error” caso haja a tentativa inválida de operar com tipos não correspondentes àquela função (e caso não haja forma de coagir algum dos tipos a se adequar à tipagem esperada). Alguns tipos bastante conhecidos são o Int, o Char, a String, o Bool, etc.

Já no caso de linguagens sem tipos (que também podem ser chamados de tipo único), como a Python, todos os habitantes do mundo são objetos, e as funções ocorrem entre objetos. Por mais que possam ter uma decoração de tipos, os objetos de Python não obedecem às regras do mundo tipado.

Nesse contexto, também é importante destacar que existe uma outra distinção realizada quando os tipos são elementos básicos da linguagem de programação em si, sendo chamados de tipos primitivos. A partir desses, outros tipos são criados e implementados nas diferentes linguagens de programação, que tem diferentes primitivos. Na maioria das linguages tipadas, também é possível criar novos tipos, definidos durante a escrita do programa.

Mas então, como ficam os Sets?

### Conjuntos como inspiração para a montagem da lógica de tipos

Em primeiro momento, há de se reconhecer a utilidade de todo o arcabouço teórico matemático garantido pela Teoria dos Conjuntos. A noção que temos de habitantes de um mundo e de relações entre esses habitantes, o que nos garante as funções computacionais de fato, bebe primordialmente da Teoria dos Conjuntos!

### Sets como coleções de coisas

Em segundo lugar, os Conjuntos (que agora chamamos de Sets) voltam a aparecer na Computação, agora sob uma nova roupagem, a de coleção de coisas. Como vimos anteriormente no segundo dia, a programação se importa bastante com a possibilidade de reunir diversas coisas em uma única estrutura.

<div style="text-align: center;"><img src="assets/images/box.jpg" alt="" style="widht:300px;height:300px;"> </div>

Nesse sentido, o Set destaca-se como uma estrutura que armazena informações e segue um ordenamento próprio. Assim, é fundamental diferenciar de forma mais qualificada, o que seria a especificação de Set, entendido enquanto Tipo Abstrato de Dados, e o que seria uma possível implementação.

### Especificação/Tipo Abstrato de Dados

Quando falamos em especificação, normalmente nos referimos à descrição pormenorizada que o cliente ofereceu do produto/aplicação/programa que ele quer. No caso dos conjuntos, estamos nos referindo à ideia abstrata do que deveria ser um conjunto, ou seja, daquilo que se comporte da forma que esperamos que se comporte um conjunto.

Dentro da Computação, chamamos de Tipo Abstrato de Dados, aqueles tipos que são conhecidos de forma abstrata enquanto regras a serem seguidas. Tudo aquilo que for implementado de forma a obedecer todas as regras esperadas pela especificação do conjunto, assim como suas operações, merecerá o nome de implementação possível de conjunto, naquele dado contexto.

### Implementação

As formas de implementar um Set são diversas. Várias linguagens de programação vem com o tipo/objeto Set disponível com uma implementação específica em suas bibliotecas, como é o caso de python e C++. Todavia, também nessas linguagens é possível implementar um tipo/objeto novo que respeite a especificação de conjuntos, mas com uma implementação distinta.

Por mais que pareça trabalhoso refazer algo já pronto, por vezes uma boa programadora, ou um bom programador, pode querer reimplementar algum tipo ou função dentro de uma determinada linguagem, buscando melhorar sua eficiência ou reduzir o consumo de memória, para aquela utilização específica. Já para fins pedagógicos, a implementação de Tipos Abstratos de Dados pode ser útil para explorar as diferenças entre essas possíveis implementações.

### Tipos de coleções semelhantes

Assim como os Sets, existem outros tipos de coleções que armazenam coisas, as quais têm regras que divergem dos Sets, mas que foram criadas a partir dele. Sendo assim, é essencial dominar o funcionamento de conjuntos antes de partir para estruturas mais complexas, uma vez que parte de princípios semelhantes, ainda que mais complexos.

Algumas coleções possíveis de serem citadas que tem estrutura que de alguma forma se assemelha a dos conjuntos são:

- Par ordenado : Composto por dois elementos ordenados, acessíveis a partir de suas posições <first,second>
- Lista finita : Composta por uma série de elementos acoplados, com início e fim
- Lista infinita : Composta por uma série de elementos acoplados, podendo ter início ou fim
- Bag/Sacola : Composta por elementos sem posição relevante, mas admitindo repetições
- Sequência : Composta por uma série de elementos acoplados e ordenados
- Dicionário/Array Associativo : Composta por vários pares ordenados de <Chave, Valor> em que as chaves são únicas e os valores são acessados a partir de suas respectivas chaves
- Pilha : Composta por elementos acoplados, com inserção no início e remoção no fim
- Fila : Composta por elementos acoplados, com inserção no início e remoção no início
- Árvore : Composta por elementos associados com a utilização de nós, com regras específicas para inserção e exclusão, de forma a garantir que a estrutura siga sendo uma árvore (a imagem abaixo é de uma árvore)

<div style="text-align: center;"><img src="assets/images/tree.png" alt="" style="widht:300px;height:300px;"> </div>

Perceba que podemos passar de uma estrutura para outra pela mudança de poucos detalhes, com as diferenças observadas tendo um grande impacto na utilidade, na eficiência e no consumo de memória de cada coleção de dados. Uma coleção ordenada terá uma busca de elemento realizada mais rapidamente do que uma coleção desordenada, por exemplo.

### Especificação elementar dos Sets

Quando falamos de Sets, esperamos que algumas coisas sempre aconteçam (no caso que o Set siga todas as regras do conjunto que conhecemos da Matemática). Nesse sentido, sempre é importante que esteja presente presente na especificação de um Set a dada estrutura:

- Unicidade dos elementos, em que elementos repetidos são indiferenciáveis
- Ausência de ordem, em que a ordem dos elementos não é relevante

Nessa estrutura, é possível que o Set seja heterogêneo ou homogêneo:

- Homogêneo: normalmente obrigatório em linguagens tipadas, sendo nececessário que todos os elementos do Set sejam do mesmo tipo
- Heterogêneo: possível nas linguagens não tipadas/unitipadas, em que os distintos elementos do Set não precisam ser do mesmo tipo

Além disso, o Set precisa garantir as dadas operações:

- Construtor de um Set vazio a partir do nada
- Construtor de um Set habitado a partir de seus elementos
- Modificador que adiciona um elemento
- Modificador que exclui um elemento
- Modificador que exclui todos os elementos, deixando o Set vazio
- Operação de acesso que verifica se o Set contém um elemento
- Operação de acesso que verifica o tamanho do Set
- Operação de acesso que verifica se o Set está vazio

Perceba a semelhança das operações do Set na Computação com o conjunto na Matemática. Não é por acaso, afinal, como abordado acima, existe uma intenção de garantir que o tipo/objeto computacional corresponda à ideia que temos em nossa cabeça do que deveria ser um conjunto!

Veja aqui um exemplo desse tipo sendo utilizado em Python e C++:

```python
s = {3, 5, True, "banana"};

s.add(7);
s.remove(5);

for n in s:
    print(n, end=" ");
```

```cpp
#include <iostream>
#include <set>

int main() {
    
    std::set<int> s = {3, 5, 2, 1};
    
    s.insert(7);
    s.erase(5);

    for (int i = 0 ; i < s.size() ; i++)
        std::cout << x << " ";
    return 0;
}
```

### Ocasiões em que Sets podem aparecer

Decerto, quando se fala em estruturas de dados e em tipos abstratos de dados, sempre estaremos discutindo qual a melhor e mais adequada ferramenta para este ou aquele objetivo. No caso dos conjuntos não é diferente, assim como nos são úteis na Matemática, eles também podem ser úteis na vida real durante a programação. 

Por vezes, quando se está programando não é possível decidir qual coleção de dados você irá utilizar. Em casos como listas de participantes com inscrições possivelmente repetidas, caso você queira checar se determinado participante deve ser admitido ou não, um Set pode ser a melhor solução. Nesse cenário seria muito custoso tratar a coleções de dados (eliminar as repetições), e por isso um Sets seria um dos tipos ideais.

Em outros casos, como quando você quer reduzir o espaço gasto, mas não quer se preocupar com repetições, também é comum usar Sets, como quando se está recolhendo espaços já visitados durante o percorrimento de um labirinto,e você necessariamente terá que passar por alguns lugares mais de uma vez.

Além disso, é também na área de dados que os Sets e as operações envolvendo conjuntos adquirem mais relevância. Mas como este minicurso é apenas introdutório iremos nos ater ao funcionamento dos conjuntos em si, a fim de que os conceitos básicos sejam dominados para que daí possam ser compreendidos assuntos mais complexos!

##### Exercício

Agora, utilizando apenas as ferramentas dispostas na especificação dos Sets, você seria capaz de criar um par ordenado?

<details>
    <summary>resposta: SPOILER!</summary>
    Resposta: {x, {x,y}}
</details>

#### List X Set
Como visto anteriormente nesse dia, vocês viram que existem algumas estruturas de dados similares aos Sets, também viram que as Listas são um exemplo disso.
Ao contrário de Sets, as listas possuem algumas propriedades específicas que tornam ela “especial”, sendo algumas delas:

- Ordem
- Acesso direto por índice
- Possibilidade de duplicatas

Apenas olhando dessa forma, vem a pergunta: Então por que utilizamos Sets?
A resposta não é tão simples, pois, o motivo de usar alguma estrutura de dados é variável. Porém, os maiores “defeitos” dos conjuntos se tornam sua “maior virtude”, visto que, o uso de Sets tem as seguintes vantagens:

- Elementos únicos.
- Bem otimizado.
- Filtragem eficiente.

Sendo assim, temos os seguintes casos para cada estrutura:

List:
- Ordem importa
- Possibilidade de elementos repetidos
- Precisa acessar elementos por índice

uso comum:

\- Histórico

\- Sequência de dados

Sets:

- Ordem não importa
- Elementos únicos
- Eficiência na busca

uso comum:

\- “Limpar” listas com possíveis duplicatas

\- Contagem de itens distintos.

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
Note que, é MUITO similar ao que estamos acostumados em Sets (no “papel”), já que segue a forma “” elemento -> condição "".
Na prática não tem diferença entre os dois códigos, porém, note que o de baixo está mais compacto e legível.
Para utilizar esse conceito em Sets não é tão diferente (obs: pode variar dependendo da linguagem, mas a lógica se mantém), em python por exemplo, a única diferença é que ao invés dos colchetes ([]) utilizamos chaves ({}).
Vantagens da sintaxe:
- O código fica menor
- O código fica mais legível para terceiros
- Geralmente é mais eficiente do que o “jeito normal”


### Funções na matemática vs Funções na programação
#### O que são funções?
Entender o que são funções é primordial para a formação de um bom programador, já que afeta diretamente nos seus códigos. Como a maioria são calouros do BTI ou do BCC, já devem ter visto, respectivamente, em ME e Cálculo 1 o que são funções na matemática. Apenas para relembrar, funções na matemática são relações entre elementos de 2 conjuntos, onde, para cada entrada, existe apenas uma saída.
Por exemplo, caso a gente tenha uma função real f (Domínio e contradomínio real), onde f(x) = x, sabemos que f(1) = 1, f(2) = 2, porém, temos também que f(21) = 42 com toda certeza está errado, já que f(21) = 21.
Analogamente, temos algumas características dessas funções que serão importantes para o futuro, sendo essas:

- Não alteram o valor de entrada 
- Para qualquer entrada, a saída sempre será a mesma. (Chamamos isso de pureza)

Sobre as funções na programação, vocês também já devem ter visto (PC ou ITP). Em resumo, na programação, funções são blocos de códigos nomeados que executam alguma tarefa onde podem ter valores de entrada e/ou saída.
Olhando rápido, podem parecer a mesma coisa, porém o ponto chave está no “podem”.
Funções na programação não são limitadas da mesma forma que as funções na matemática, temos por exemplo as seguintes características:

- PODEM alterar o valor de entrada
- PODEM variar o valor de saída (impureza)

Funções na programação são como quests pequenas em uma questline de um jogo de RPG, onde cada quest pequena tem um objetivo definido, e logo após terminar ela, voltamos para a questline principal com suas recompensas.

#### Pontos em comum
Como visto anteriormente, as funções na programação tem a possibilidade de manter as características das funções matemáticas, nos permitindo dizer que temos os seguintes pontos em comum:

- Ambas recebem valores de entrada.
- Ambas podem retornar algum valor de saída.
- Ambas ajudam a abstrair a complexidade e organizar pensamentos.

E com isso, temos um novo tópico:

#### Aplicação de funções matemáticas na programação

A noção de “pureza” que vimos anteriormente será crucial para definir quando uma função será útil.
Funções puras, onde o valor de saída sempre é o mesmo para as mesmas entradas, são ideais para cálculos e transformações de dados, já que garantem resultados exatos e previsíveis.
Portanto, ao trabalhar com transformações de dados, observar um modelo de uma função matemática facilita não só na lógica, mas também na sua aplicação e confiabilidade.




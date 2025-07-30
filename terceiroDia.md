---
layout: layoutGit
title: Minicurso de Linux e Git
---


<div id="sumario" class="sumario-git">
    <h1>Sumário</h1>
    <ul>
    <details>
        <summary><a href="#relações-de-congruência">Relações de Congruência</a></summary>
        <ul class="section-content">
            <li><a href="#o-que-é-um-processo">Conceitualização?</a></li>
            <li><a href="#relações-de-congruência-na-programação">Relações de congruência na programação</a></li>
            <li><a href="#aplicações-e-definição-formal">Aplicações e definição formal</a></li>
            <li><a href="#propriedades">Propriedades</a>></li>
        </ul>
    </details>
    <details>
  <summary><a href="#criptografia-rsa">Criptografia RSA</a></summary>
    <ul class="section-content">
        <li><a href=""></a></li>
        <li><a href=""></a></li>
    </ul>
  </details>
</ul>

  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
  
  </div>

# Relações de congruência 

## Conceitualização
No Brasil, usamos o sistema de 24 horas, mas, coloquialmente, chamamos o horário das 18h por “6 da tarde”, ou o horário das 17h por “5 da tarde”. De onde exatamente saíram esse 6 e esse 5? Você pode argumentar que são 6 horas após o meio-dia (12h), ou seja, 12 + 6 = 18h, e você estaria correto, isso se trata de uma relação de congruência! 
O relógio de ponteiro só vai até as 12, mas mesmo assim conseguimos ler através dele as 24 horas do dia. Relações de congruência funcionam como relógios, da mesma forma que podemos dizer que 18h equivale a 6h (da tarde) no formato de 12h, dizemos que 18 ≡ 6 (mod 12). As relações de congruência estão diretamente ligadas aos comportamentos “cíclicos” de como enxergamos o mundo, outros exemplos são os dias da semana, dias no mês ou até mesmo as bases numéricas (como a base 10 que usamos)! Tente identificar relações de congruência nos exemplos dados.

## Relações de congruência na programação
Na computação, utilizamos vastamente relações de congruência para as mais diversas finalidades.
O operador ‘%’ (módulo) retorna o resto de uma divisão, o que é a base para as relações de congruência. Utilizando nosso exemplo do relógio, podemos utilizar o operador ‘%’ para descobrir que horário no relógio é equivalente a nossa entrada no formato 24h.
```python
# Exemplo 1: Ciclos de 12 horas (relógio)

# Qual horário corresponde as 18h?
print(18 % 12)  # Saída: 6 → 18 ≡ 6 (mod 12)

# Qual horário corresponde as 23h?
print(23 % 12)  # Saída: 11 → 23 ≡ 11 (mod 12)
``` 
Para checar se dois números são congruentes (em relação a um módulo m), basta checar se o resto que eles deixam na divisão por m é o mesmo.
```python
# Exemplo 2: Checando se dois números são congruentes em relação a um módulo

a = 38
b = 14
m = 12
print(a % m == b % m)  # True, pois 38 ≡ 14 ≡ 2 (mod 12)

```
Uma aplicação mais concreta e amplamente utilizada é descobrir se um número é par ou ímpar. Se dividirmos qualquer número por 2, existem apenas duas possibilidades: ou o resto é 0, ou o resto é 1. 
```python
# Exemplo 3: Restos deixados na divisão por 2
print(8 % 2) # Saída: 0
print(9 % 2) # Saída: 1
print(255 % 2) # Saída: 1
print(1798 % 2) # Saída: 0
```
Os números pares são as classes de equivalência de 0 módulo 2 (mais sobre isso futuramente), podemos abusar desse fato para classificar pares e ímpares facilmente, se deixa resto 0 significa que é par, se deixa resto 1, significa que é ímpar.
```python
# Exemplo 4: função para verificar se um número é par

def eh_par(numero):
   if numero % 2 == 0:
      return true # O número é par
   if numero % 2 == 1:
      return false # O numéro não é par (ou seja, é impar) 
```
 Da mesma forma que fizemos no exemplo acima, podemos usar o exemplo 2 para definir uma função recebe 2 números e um módulo, e retorna se aqueles números são congruentes em relação aquele módulo.
```python
# Exemplo 5: função para verificar se dois números são congruentes em relação a um módulo

def congruente(a, b, m):
   if (a % m) == (b % m):
      return true
   else:
      return false:
```

## Aplicações e Definição formal
A ideia principal por trás das relações de congruência é mostrar que dois números são equivalentes numa divisão por um número m se, ao serem divididos por m, eles deixam o mesmo resto. Por exemplo quando dividimos 6 por 4, obtemos resto 2 (6 mod 4 = 2), e da mesma forma, quando dividimos 10 por 4 também obtemos resto 2 (10 mod 4 = 2), assim, dizemos que 6 equivale a 10 (ou que 6 é congruente a 10) numa divisão por 4. Esse conceito tem diversas aplicações práticas, como:

1. Criptografia
 - Algoritmos como RSA usam congruências modulares para codificar/decodificar mensagens (ex: cálculo de c ≡ m^e mod n para cifragem). [Idéia: implementar em python um algorítmo de cifra de césar simples]
2. Validação de documentos
 - Dígitos verificadores do CPF, cartões de crédito ou até contas bancárias utilizam congruências modulares
3. Hash tables
 - Funções hash utilizam o operador '%' para mapear chaves em índices de arrays


### Definição Formal
Dados a,b e m inteiros, e m > 0, dizemos que:
a ≡ b (mod m) se e somente se m | (a - b)
Exemplos:
- 15 ≡ 3 (mod 12), pois 12 \| (15 - 3)
- 6 ≡ 2 (mod 4), pois 4 \| (6 - 2)
- 19 ≡ 5 (mod 7), pois 7 \| (19 - 5)

## Propriedades
Agora, vamos ver algumas propriedades fundamentais das relações de equivalência, e demonstrar que elas valem. 
**Propriedades relacionais:**
1. Reflexividade: a ≡ a (mod m)
2. Simetria: a ≡ b (mod m) → b ≡ a (mod m)
3. Transitividade: a ≡ b (mod m) e b ≡ c (mod m) → a ≡ c (mod m)

**Propriedades operacionais:**
*Se a ≡ b (mod m) e c ≡ d (mod m), então.*
1. Adição: a + c  ≡ b + d (mod m)
2. Subtração: a - c ≡ b - d (mod m)
3. Multiplicação: a * c ≡ b * d (mod m)

## Classes de Equivalência
~ melhorar ainda

# Criptografia RSA
Historicamente, "esconder" mensagens sempre foi uma necessidade: passar informações para aliados de maneira segura, - sem a possibilidade delas serem roubadas - era imprescindível durante episódios como guerras ou conflitos. Nesse contexto, foram desenvolvidas técnicas para que essas mensagens pudessem passar despercebidas ou ininteligíveis diante do olho inimigo, mas claras para os destinatários.

A esteganografia, por exemplo, já é utilizada há milhares de anos. O seu nome vem das palavra gregas "steganos", que significa "coberta", e "graphein", que significa "escrever" - e, como as definições sugerem, a prática se reduz a encobrir a existência dessas mensagens por completo, de forma que elas passem despercebidas a um olho destreinado.

Durante as Guerras Persas, (cerca de 500-450 AC!) o governante Histieu de Mileto já se utilizava da esteganografia: prisioneiro do rei da Pérsia e na necessidade de passar mensagens para o seu exército na Grécia, ele raspou a cabeça de um mensageiro, tatuou a mensagem em seu couro cabeludo, e esperou o cabelo crescer de novo. Com a mensagem encoberta, o mensageiro poderia viajar sem nenhum problema pelas terras e, quando chegasse em seu destino, rasparia a sua cabeça de novo para informar as ações que deveriam ser tomadas pelos gregos.

Ainda que completamente inaplicável em grande escala (convenhamos, nem todos temos tempo o suficiente de esperar cabelo crescer para mandarmos mensagens. Ou espaço o suficiente em nossos couros cabeludos.), essa ação já mostrava a aplicação da esteganografia para passar mensagens de maneira segura (e ineficiente). Mas não para por aí! Ainda na Grécia, tabuletas de cera eram raspadas, escritas sobre e depois cobertas com cera de novo para passarem despercebidas. Já na China antiga, mensagens eram escritas em tiras finas de seda e amassadas e cobertas por cera - os mensageiros, então, engoliam as bolinhas para transportá-las.

Mas o problema com essas práticas era claro: assim que alguém prestasse mais atenção, pensasse em raspar a cera de uma tábua ou checasse a cabeça de alguém, ía tudo pro beleléu.

Então, à medida que a "comunicação secreta" continuou a evoluir, outra forma de passar essas mensagens foi desenvolvida - a criptografia ("cryptos", também do grego, significa "escondido"). Assim, ao invés de tentar acobertar uma mensagem, os esforços seriam direcionados para esconder o seu significado - processo conhecido como cifragem ou encriptação. Ou seja, uma mensagem seria embaralhada ou modificada com base em uma regra ou em um protocolo pré-definido, de forma que a pessoa que vai receber a mensagem consiga fazer um outro processo para desembaralhar essa mensagem e torná-la inteligível (o que ficaria difícil para alguém que não é o destinatário da mensagem fazer). Durante esse processo, é utilizada uma chave - ela que será a responsável por manter a mensagem secreta, mesmo que o algoritmo seja conhecido!

Uma das criptografias mais conhecidas é a chamada "Cifra de César", usada durante as Guerras da Gália pelo Império Romano. Nela, Júlio César (ou o seu representante) simplesmente substituía cada letra da mensagem pela letra 3 casas depois no alfabeto (nesse caso, a chave seria 3!).

*imagem cifra de césar*

Diversas variações dessa cifra existem - e enquanto sim, só existem 25 diferentes possibilidades triviais de chaves, não se engane! Há cerca de 400,000,000,000,000,000,000,000,000 chaves diferentes caso o alfabeto seja rearranjado; Se levássemos um segundo para checar cada uma das possibilidades, esse processo duraria cerca de um bilhão de vezes o tempo de vida do universo!

Com a modernização da área, foram criados diversos outros sistemas de criptografia, cada vez mais modernos e seguros - um deles sendo a Criptografia RSA (Rivest-Shamir-Adleman), que estudaremos um pouquinho mais a fundo a seguir!

– CRIPTOGRAFIA RSA

Os três cientistas em questão (Ron Rivest, Adi Shamir e Leonard Adleman) eram do departamento de Ciência da Computação do MIT, e estavam tentando resolver um problema de criptografia assimétrica - proposto anteriormente por cientistas em Harvard. De mai
os problemas encontrados com a criptografia simétrica eram
os processos de criptografia e decriptografia eram objetivamente o inverso um do outro
esconder a chave

Até então, todas as formas de criptografia eram simétricas, - ou seja, o processo de “decriptação” era objetivamente o inverso da “encriptação”. Assim, ambos usavam a mesma chave - o que facilitaria o roubo de informações, já que a chave deveria ser transportada para que o conteúdo pudesse ser revelado! Justamente para tentar mitigar esse problema, Whitfield Diffie e Martin Hellman (dois Cientistas da Computação e oeiroefr de iafiaer,) idealizaram uma maneira diferente de transportar mensagens secretas: a Criptografia Assimétrica.

Na criptografia assimétrica, ao invés de apenas uma chave, duas chaves são necessárias: uma pública, para a encriptação, e uma privada, para a decriptação. Dessa forma, cada usuário disponibiliza a sua chave pública, de forma que qualquer um pode criptografar mensagens para ele, e mantém em segredo a sua chave privada, para que ele seja o único capaz de descriptografar o que lhe foi enviado. O maior objetivo, então, seria facilitar ao máximo a primeira etapa e dificultar ao máximo a segunda (a não ser que a chave secreta esteja em sua posse!). Ou seja, o problema da necessidade de transportar a chave de maneira segura (para que a mensagem não seja roubada) some!

Para explicar mais claramente essa ideia, vamos imaginar que Alice precisa mandar uma mensagem para Bob. Então, ambos terão disponibilizado suas chaves públicas e escondido suas chaves privadas. Mas vamos também imaginar que Eve quer bisbilhotar as mensagens que eles estão mandando entre si, esse processo precisa ser feito da maneira mais segura possível.

Para Alice criptografar uma mensagem e enviá-la para Bob, ela vai usar a chave pública oferecida por ele para deixar a mensagem ininteligível. Eve, por mais que ela queira descobrir o que foi mandado, não vai conseguir fazer com que a mensagem passe a ser compreensível, porque ela não tem a chave secreta! Bob, assim que receber a mensagem, vai usar a chave secreta que ele tem para decriptar a mensagem.

Até simples de entender, né? Mas um processo que possibilitasse essa propriedade demorou anos a ser desenvolvido! Foi apenas em 1977 que Ron Rivest, Adi Shamir e Leonard Adleman foram capazes de publicar suas descobertas e uma nova forma de criptografar: a chamada Criptografia RSA. 

A segurança desse sistema se baseia tanto na infinidade dos números primos quanto na dificuldade para a fatoração em primos.

– explicar em geral porque funciona (usar mod-> dificil de reverter)
– exemplificar com alice e bob

Cada pessoa, para criar as suas próprias chaves, escolherá dois números primos - que chamaremos de P e Q. A chave pública, que chamaremos de N, será a multiplicação entre esses 2 números. Então, por exemplo, para um p = 17 159 e um q = 10 247, temos N = p ✕ q = 175 828 273. Esse N será, então, utilizado para criptografar a nossa mensagem 

Digamos que Alice tenha escolhido p = 7 e q = 13;

vale ressaltar que, com a evolução exponencial dos computadores nos últimos 50 anos, esse tipo de tecnologia não é mais considerado tão seguro, já que se baseia na dificuldade de fatoração de primos!

Para explicar, voltaremos à ideia de Alice e Bob

No entanto, Eve quer bisbilhotar essa mensagem





A ideia de um sistema assimétrico de criptografia seria justamente mitigar esse problema, de forma que a chave não precisasse ser transportada para quem vai receber a mensagem. Inicialmente isso pode ser difícil de imaginar, mas vamos pensar no seguinte: imagine que 

vamos imaginar que Alice está tentando mandar uma mensagem para Bob. 

---

<script>
const dataDia3 = new Date('2025-03-12');
const agora = new Date();

if (agora < dataDia3) {
    document.body.innerHTML = '<h1 style="text-align:center; margin-top:20%;">Página Indisponível</h1>' +
                              '<p style="text-align:center;">Esta página estará disponível a partir de ' + dataDia3.toLocaleDateString() + '.</p>';
}
</script>
{% include petcccopyright.html %}

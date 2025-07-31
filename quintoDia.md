---
layout: layoutGit 
title: Minicurso de Linux e Git
---

# Projeto final

<div id="sumario" class="sumario-git">
    <h1>Dia 5</h1>
    <summary><a href="#Projeto final">Projeto final</a></summary>
    <ul>
      <li><a href="#Orientações gerais">Orientações Gerais</a></li>
      <li><a href="#Pontos essenciais">Pontos essenciais</a></li>
      <li><a href="#Critérios de avaliação">Critérios de avaliação</a></li>
      <li><a href="#Problema 1">Problema 1</a></li>
      <li><a href="#Problema 1">Problema 1</a></li>
      <li><a href="#Problema 2">Problema 2</a></li>
      <li><a href="#Problema 3">Problema 3</a></li>
      <li><a href="#Problema 4">Problema 4</a></li>
    </ul>
  <button class="toggle-button" id="toggle-button">
  
      Esconder Sumário
  
  </button>
  </div>

## Orientações gerais:

1) A partir do apresentado, elabore um plano de como a sua equipe solucionaria a atual demanda, indicando cada passo a ser seguido e quais os sub-problemas identificados;

2) Programe superficialmente um protótipo do sistema requisitado, em pseudocódigo ou em alguma linguagem de programação de sua escolha, que seja capaz de atender de forma eficiente a situação em análise;

3) Faça uma apresentação a todo o corpo de colaboradores presentes, esmiuçando os pontos-chaves essenciais à continuidade de ações que garantam um produto final.

## Pontos que devem estar presentes na apresentação da solução alcançada:

1) Aspectos observados ao decorrer da solução que se aproximam de conceitos matemáticos vistos nesse curso;

2) Explicação detalhada da lógica por trás do pseudocódigo ou código utilizado;

3) Checagem de possíveis problemas que podem ocorrer na implementação;

4) Aplicação em um caso teste hipotético;

## Critérios de Avaliação:

1) Entendimento satisfatório da situação problema;

2) Domínio do código usado como solução;

3) Boa escolha de caso teste;

4) Didaticidade e clareza na hora de apresentar a solução encontrada;

5) Corretude matemática dos algoritmos implementados;

6) Boas práticas e documentação;

## Situação Problema 1: Números bloqueados

Você é encarregado de solucionar a seguinte problemática:

Determinado usuário da empresa faz-tudo para a qual você presta serviços tem recebido uma quantidade excessiva de ligações spam. Ao perceber que muitas dessas ligações eram de números repetidos, o usuário solicitou uma aplicação que fosse capaz de bloquear essas chamadas.

Sendo parte da equipe que ficou com essa demanda, você precisa criar um sistema que armazene os números de telefones bloqueados e, baseando-se nessa coleção de dados, seja capaz de bloquear as chamadas provenientes dos números listados.

A sua equipe deve entregar as seguintes funções implementadas:

- O construtor da estrutura de dados que armazena os números
- Uma função que verifica a presença ou ausência do número na lista
- Uma função que adiciona novos números
- Uma função que remove um número
- Uma função auxiliar que bloqueia chamadas de números presentes na estrutura de dados

---
<script>
const dataDia5 = new Date('2025-03-13');
const agora = new Date();

if (agora < dataDia5) {
    document.body.innerHTML = '<h1 style="text-align:center; margin-top:20%;">Página Indisponível</h1>' +
                              '<p style="text-align:center;">Esta página estará disponível a partir de ' + dataDia5.toLocaleDateString() + '.</p>';
}
</script>
{% include petcccopyright.html %}

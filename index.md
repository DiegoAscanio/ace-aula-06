<style>
  section {
    background: #fff url(./img/background.png) no-repeat center center;
    background-size: cover;
  }

  .transparent {
    background-color: transparent!important;
  }

  section.transparent img {
    background-color: transparent!important;
  }

  .transparent-table-tr-td-th {
    background-color: rgba(0, 0, 0, 0.0) !important;
  }

  .cabecalho {
    position: absolute;
    top: 10%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 48px;
    font-weight: bold;
  }

  .conteudo {
    top: 30%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 28px;
    text-align: justify;
  }

  .conteudo-absoluto {
    position: absolute;
    top: 30%;
    margin-left: 5%;
    margin-right: 10%;
    font-size: 28px;
    text-align: justify;
  }
  
  .large {
    font-size: 36px;
  }

  .normal {
    font-size: 22px;
  }
  .regular {
    font-size: 18px;
  }
  .small {
    font-size: 16px;
  }
  .footnotesize {
    font-size: 14px;
  }
  .scriptsize {
    font-size: 12px;
  }
  .tiny {
    font-size: 10px;
  }
  .bold {
    font-weight: bold;
  }
  .center {
    text-align: center;
  }
  section.lead p {
    text-align: justify;
    font-size: 22px;
  }
  section.lead li {
    text-align: justify;
    font-size: 22px;
  }

  section.lead h1 {
    text-align: center;
  }
  section.lead h2 {
    text-align: center;
  }
  
  .grid-50-50 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    text-align: justify;
  }

  .grid-66-33 {
    display: grid;
    grid-template-columns: 2fr 1fr;
    text-align: justify;
  }

  .grid-33-66 {
    display: grid;
    grid-template-columns: 1fr 2fr;
    text-align: justify;
  }

  .grid-element {
    margin-left: 5%;
    margin-right: 5%;
  }
  img[alt=grid-img] {
    width: 100%;
  }

</style>

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>


# Análise de Circuitos Elétricos
## Aula 06 - Circuitos de Primeira Ordem
 
Prof. M.Sc. Diego Ascânio Santos (ascanio@cefetmg.br)

Aula baseada sobre o material do professor Dr. Emerson Gonçalves de Melo (emerdemelo@usp.br - DEMAR EEL USP), da professora Drª. Thabatta Moreira Alves de Araújo (thabatta@cefetmg.br - DIGDDV) e da Khan Academy.

CEFET-MG DIGDDV - Divinópolis, 2023.


---

## Roteiro

1. Definição
2. Estados Permanentes e Estados Transitórios
3. Estímulo Natural
4. Estímulo Degrau
5. Resposta Natural do Circuito RC
6. Resposta Natural do Circuito RL
7. Resposta ao Degrau do Circuito RC
8. Resposta ao Degrau do Circuito RL


---

## DEFINIÇÃO

Circuitos de primeira ordem são circuitos que possuem apenas um elemento (capacitor ou indutor) de armazenamento de energia em série a um elemento resistivo (resistor).

Até o momento, conhecemos somente as grandezas presentes em um acumulador de energia (tensão, corrente, potência e energia) mas, não entendemos os processos que determinam como tais elementos acumulam ou fornecem energia.

Para isso, precisamos definir os conceitos de estados transitórios e permanentes, o conceito de estímulos (natural e degrau) e introduzir as respostas de capacitores e indutores a tais estímulos.


---

## Estados Permanentes e Estados Transitórios

### Estado Permanente

<!-- _class: lead -->
Considere um acumulador passivo de energia (Capacitor ou Indutor). O estado permanente refere-se às condições (valores de tensão, corrente, potência e/ou energia) deste acumulador após um período suficientemente longo, durante o qual perturbações ou mudanças imprevistas já cessaram.

### Exemplos de estados permanentes:

<!-- _class: lead -->
1. Capacitores se comportarem como malhas abertas em circuitos CC (após terem sido carregados acumulando energia na forma de campo elétrico);
2. Indutores se comportarem como curtos-circuitos em circuitos CC (após terem sido carregados acumulando energia na forma de campo magnético);
3. Capacitores e Indutores descarregados e desconectados de qualquer fonte de energia;


---

## Estados Permanentes e Estados Transitórios

### Estados Transitórios

<div class="regular">
Referem-se às condições dos passivos de energia enquanto acumulam ou fornecem energia de forma transitoria. Estes estados surgem de perturbações que interrompem o estado permanente pré-existente do sistema.
</div>

<div style="margin-left: 5%; margin-right: 5%; margin-top: 5%; margin-bottom: 5%; box-shadow: inset 0px 0px 5px 5px #888888;" class="regular">

<div style="margin: 3% 3% 3% 3%;">

Estamos interessados em modelar o comportamento transitório dos passivos de energia em circuitos de primeira ordem \\(RL \text{ | } RC\\). por serem circuitos de 1ª ordem, é possível modelar estes circuitos através de equações diferenciais de ordem 1. porém, antes de modelar os circuitos, temos de entender que a transitoriedade so existe em resposta a um estímulo que causa uma perturbação a um sistema que até um instante de tempo \\( T = 0 \\) se encontrava em um estado permanente.

A priori, estudaremos dois destes estímulos:

1. Natural
2. Degrau

</div>

</div>

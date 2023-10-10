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
    display: block;
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

Estamos interessados em modelar o comportamento transitório dos passivos de energia em circuitos de primeira ordem \\(RL \text{ | } RC\\). Por serem circuitos de 1ª ordem, é possível modelar estes circuitos através de equações diferenciais de ordem 1. porém, antes de modelar os circuitos, temos de entender que a transitoriedade so existe em resposta a um estímulo que causa uma perturbação a um sistema que até um instante de tempo \\( T = 0 \\) se encontrava em um estado permanente.

A priori, estudaremos dois destes estímulos:

1. Natural
2. Degrau

</div>

</div>


---

## Estímulo Natural (Representa a Descarga)

<div class="normal">

- Representa perturbações que levam um passivo de energia a fornecer (descarregar) energia para um passivo de resistência.
- Queremos saber como o passivo de energia descarrega, modelando sua resposta natural.
- O estímulo natural é causado pela retirada repentina de uma fonte constante de tensão (corrente) conectada ao passivo de energia e pela ligação (imediata) deste passivo à uma carga resistiva.

<div class="grid-66-33">

<div class="grid-element">

- Exemplo de perturbação que leva um capacitor a descarregar: Um circuito onde a chave seletora estava a longo tempo na posição \\(a\\) e então, comuta para a posição \\(b\\) quando \\(t = 0\\).

</div>

<div class="grid-element">

<!-- _class: transparent -->
![](./img/rc-natural.png)

</div>

</div>


---

## Estímulo Degrau (Representa a Carga)

<div class="regular">

- Representa perturbações causadas por uma fonte constante e contínua de tensão (corrente) que levam um passivo de energia a acumular (carregar) energia em si.
- Se queremos saber como um passivo de energia carrega, modelamos sua resposta ao degrau.
- O estímulo ao degrau representa a aplicação repentina de uma fonte de tensão (corrente) constante a um acumulador de energia (novamente, capacitor ou indutor).

<div class="grid-66-33">

<div class="grid-element">

- Exemplo de perturbação que leva um capacitor a carregar: Um circuito onde a chave estava a longo tempo desligada e no instante \\(t = 0\\) é ligada, fazendo com que uma fonte de corrente constante seja conectada ao capacitor.

</div>

<div class="grid-element">

<!-- _class: transparent -->
![](./img/rc-degrau.png)

</div>

</div>

</div>


---

## Resposta Natural do Circuito RC

<div class="grid-66-33">

<div class="grid-element normal">

- Uma vez que em \\(t = 0\\) a chave comuta de \\(a\\) para \\(b\\), logo, o capacitor \\(C\\) fica conectado, fornecendo energia, à resistência \\(R\\) como visto na segunda imagem à direita.
- Estamos interessados em aprender como o capacitor se comporta em resposta ao estímulo natural, ou seja, queremos saber como o capacitor descarrega.
- Existe algum modelo matemático que descreva este comportamento?
    - Sim, existe e este modelo será estudado agora!

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-natural-circuito-equivalente.svg)

</div>

</div>


---

## Resposta Natural do Circuito RC

<div class="grid-66-33">

<div class="grid-element regular">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Capacitor</strong>

Considere o circuito RC equivalente à configuração do sistema quando \\(t = 0\\) (segunda imagem a direita). Como podemos observar, no nó \\(A\\) deste circuito, existem duas correntes que saem dele: 

1. Corrente de deslocamento \\(I_{C}\\) do capacitor, ocasionada pela variação da diferença de potencial do capacitor causada pela sua descarga;
2. Corrente elétrica \\(I_{R}\\) que passa pelo resistor, oriunda da diferença de potencial \\(V_{g}\\) presente nos terminais do capacitor \\(C\\).

Em seguida, vemos que não entra nenhuma corrente no nó \\(A\\). Logo, pela Lei de Kirchoff das Correntes no nó \\(A\\), temos que:

<div class="normal">

\\[
0 = I_{C} + I_{R}
\\]

</div>


</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-natural-circuito-equivalente.svg)

</div>

</div>


---

## Resposta Natural do Circuito RC

<div class="grid-66-33">

<div class="grid-element small">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Capacitor</strong>

Reiterando, sabemos pela Lei de Kirchoff das Correntes no nó \\(A\\), que: \\(0 = I_{C} + I_{R}\\).

Sabemos que \\(I_{R} = {V \over R}\\) e \\(I_{C} = C {{dV} \over {dt}}\\). Logo: 

\\[{C {{dV} \over {dt}}} + {V \over R} = 0 \rightarrow {C {{dV} \over {dt}}} = - {V \over R}\\]

Multiplicando ambos os lados da equação por \\({{dt} \over {VC}}\\), integrando ambos os lados de \\(t_{0}\\) a \\(t\\) (considerando que \\(t_{0} = 0\\)) e cientes que \\(ln(a) - ln(b) = ln({a \over b})\\), temos uma equação diferencial de primeira ordem homogênea e separável:

<div class="grid-50-50" style="border-style: solid;">

<div class="grid-element">

\\[
\begin{align}
{{dV} \over {V}} &= - {{dt} \over {RC}} \rightarrow \\\\
\int_{V(0)}^{V(t)} {{dV} \over {V}} &= \int_{0}^{t}{- {{dt} \over {RC}}} \rightarrow \\\\
ln(V(t)) - ln (V(0)) &= {{-t} \over {RC}} - 0 \rightarrow \\\\
ln({{V(t)} \over {V(0)}}) &= {{-t} \over {RC}}
\end{align}
\\]

</div>

<div class="grid-element">

Colocando ambos os lados da equação como expoentes de \\(e\\):

\\[
\begin{align}
{{V(t)} \over {V(0)}} &= e^{{{-t} \over {RC}}} \rightarrow \\\\
V(t) &= V(0) \cdot e^{{{-t} \over {RC}}}
\end{align}
\\]

</div>


</div>



</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-natural-circuito-equivalente.svg)

</div>

</div>


---

## Resposta Natural do Circuito RC

<div class="grid-50-50">

<div class="grid-element small">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Capacitor</strong>

Como resolvemos a EDO e encontramos a equação que rege a tensão de um capacitor, a partir da lei de Ohm conseguimos encontrar as demais grandezas do sistema, como a corrente \\(I_{R}\\) que passa pelo resistor \\(R\\), a potência \\(p\\) dissipada em \\(R\\) (fornecida pelo capacitor \\(C\\)) e a energia \\(w\\) consumida pelo resistor \\(R\\) (fornecida pelo capacitor \\(C\\)\):

\\[
\begin{align}
    i(t) &= {{v(t)} \over {R}} = {{V(0)} \over {R}} e^{{{-t}\over{RC}}}, t \geq 0^{+}, \\\\
    p(t) &= Vi = {{V(0)^{2}} \over {R}} e^{{{-2t}\over{RC}}}, t \geq 0^{+}, \\\\ 
    w(t) &= \int_{0}^{t}{p dx} = \int_{0}^{t}{{{V(0)^{2}} \over {R}} e^{{{-2t}\over{RC}}} dx} \\\\
         &= {1 \over 2}C{V(0)}^{2}(1 - e ^ {{-2t} \over {RC}}), t \geq 0.
\end{align}
\\]

Nas funções exponencias presentes em todas as equações verificamos que existe um coeficiente \\(RC\\) associado a \\(t\\). Esse coeficiente é conhecido como constante de tempo \\(\tau\\) (tau) dos circuitos de primeira ordem e tal coeficiente determina o quão rápida (ou lenta) será a descarga do capacitor em uma configuração \\(RC\\).

</div>

<div class="grid-element">
<div class="grid-50-50 tiny">
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_tensao_natural_rc.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Tensão do Capacitor durante a resposta natural do circuito RC
</div>

</div>
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_corrente_natural_rc.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Corrente do Capacitor durante a resposta natural do circuito RC
</div>

</div>
</div>

<div class="grid-50-50 tiny">
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_potencia_natural_rc.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Potência fornecida pelo Capacitor durante a resposta natural do circuito RC ao longo do tempo
</div>

</div>
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_energia_natural_rc.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Energia Consumida pelo Resistor durante a resposta natural do circuito RC ao longo do tempo
</div>

</div>
</div>

</div>


---

## Determinação da Resposta Natural de um Circuito RC
### Exemplo 7.3 Livro Nilsson e Riedel 10ª Edição

<iframe src="https://diegoascanio.github.io/jupyterlite/lab?path=exemplo-7.3.ipynb" width=100% height=100%></iframe> 

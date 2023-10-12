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

  .grid-25-25-25-25 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    text-align: justify;
  }

  .grid-33-33-33 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    text-align: justify;
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
9. Solução Geral Para Respostas a um Degrau e Natural


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


---

## Resposta Natural do Circuito RL

<div class="grid-66-33">

<div class="grid-element regular">

- Quando a chave é desconectada em \\(t = 0\\), ocorre uma variação na corrente, visto que a fonte de corrente \\(I_{S}\\) é desconectada do sistema.
- O circuito que durante \\(t < 0\\) correspondia à primeira imagem da direita, passa a corresponder à segunda quando \\(t \geq 0\\).
- O indutor que antes se comportava como um curto circuito no sistema e que estava previamente carregado — armazenando energia magnética — agora fará oposição (como esperado) à variação da corrente, produzindo (a partir da energia eletromagnética que armazenou) uma corrente elétrica que se opõe à variação de corrente causada pela desconexão de \\(I_{S}\\) em \\(t = 0\\).
- Cientes de que queremos entender como o indutor responde ao estímulo natural — como ele descarrega — vamos construir o modelo matemático para descrever tal resposta.

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rl-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rl-resposta-natural-circuito-equivalente.png)

</div>

</div>


---

## Resposta Natural do Circuito RL

<div class="grid-66-33">

<div class="grid-element regular">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Indutor</strong>

Considere o circuito \\(RL\\) equivalente à configuração do sistema quando \\(t = 0\\) (segunda imagem a direita). Pela lei de Kirchoff das Tensões nas Malhas, sabemos que a diferença de potencial do Indutor somada à diferença de potencial do resistor é igual a \\(0\\):

<div class="normal">

\\[
\begin{align}
V_{L} + V_{R} &= 0 \therefore \\\\
L {{di} \over {dt}} + Ri &= 0
\end{align}
\\]

</div>

Aplicando as manipulações algébricas necessárias — colocando o termo \\(RI\\) à direita da igualdade e multiplicando ambos os lados da equação por \\({{dt} \over {Li}}\\) — obtemos a seguinte EDO de 1ª Ordem:

<div class="normal">

\\[
{{di} \over {i}} = - {R \over L} dt
\\]

</div>


</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rl-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rl-resposta-natural-circuito-equivalente.png)

</div>

</div>


---

## Resposta Natural do Circuito RL

<div class="grid-66-33">

<div class="grid-element small">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Capacitor</strong>

Integrando ambos os lados da EDO \\({{di} \over {i}} = - {R \over L} dt\\) de \\(t_{0}\\) a \\(t\\) (considerando que \\(t_{0} = 0\\)) e cientes que \\(ln(a) - ln(b) = ln({a \over b})\\), temos:

<div class="grid-50-50" style="border-style: solid;">

<div class="grid-element">

\\[
\begin{align}
{{di} \over {i}} &= - {R \over L} dt \rightarrow \\\\
\int_{I(0)}^{I(t)} {{di} \over {i}} &= \int_{0}^{t}{- {R \over L} dt} \rightarrow \\\\
ln(I(t)) - ln (I(0)) &= - {R \over L} t - 0 \rightarrow \\\\
ln({{I(t)} \over {I(0)}}) &= - {R \over L} t \rightarrow
\end{align}
\\]

</div>

<div class="grid-element">

Colocando ambos os lados da equação como expoentes de \\(e\\):

\\[
\begin{align}
{{I(t)} \over {I(0)}} &= e^{- {R \over L} t} \rightarrow \\\\
I(t) &= I(0) e^{- {R \over L} t}
\end{align}
\\]

</div>


</div>



</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rl-natural.png)

<!-- _class: transparent -->
![grid-img](./img/rl-resposta-natural-circuito-equivalente.png)

</div>

</div>


---

## Resposta Natural do Circuito RL

<div class="grid-50-50">

<div class="grid-element small">

<strong>Construção do modelo da descarga — RESPOSTA NATURAL — de um Indutor</strong>

Como resolvemos a EDO e encontramos a equação que rege a corrente de um indutor, a partir da lei de Ohm conseguimos encontrar as demais grandezas do sistema, como a tensão \\(V_{R}\\) que passa pelo resistor \\(R\\), a potência \\(p\\) dissipada em \\(R\\) (fornecida pelo indutor \\(L\\)) e a energia \\(w\\) consumida pelo resistor \\(R\\) (fornecida pelo indutor \\(L\\)\):

\\[
\begin{align}
V_{R}(t) &= I(0) R e^{-{R \over L} t}, t \geq 0^{+}, \\\\
P(t) &= I(0)^2 R e^{-2{R \over L} t}, t \geq 0^{+}, \\\\
W(t) &= {1 \over 2} {L I(0)^2}(1 - e^{-2{R \over L} t}), t \geq 0^{+}
\end{align}
\\]

Nas funções exponencias presentes em todas as equações verificamos que existe um coeficiente \\({R \over L}\\) associado a \\(t\\). Esse coeficiente é conhecido como constante de tempo \\(\tau\\) (tau) dos circuitos de primeira ordem e tal coeficiente determina o quão rápida (ou lenta) será a descarga do indutor em uma configuração \\(RL\\).

</div>

<div class="grid-element">
<div class="grid-50-50 tiny">
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_corrente_natural_rl.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Corrente do Indutor durante a resposta natural do circuito RL
</div>

</div>
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_tensao_natural_rl.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Tensão do Resistor durante a resposta natural do circuito RL
</div>

</div>
</div>

<div class="grid-50-50 tiny">
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_potencia_natural_rl.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Potência fornecida pelo Indutor durante a resposta natural do circuito RL ao longo do tempo
</div>

</div>
<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/grafico_resposta_energia_natural_rl.png)

<div style="text-align: center; margin-top: -7.5%;">
Gráfico da Energia Consumida pelo Resistor durante a resposta natural do circuito RL ao longo do tempo
</div>

</div>
</div>

</div>


---

## Determinação da Resposta Natural de um Circuito RL
### Exemplo 7.1 Livro Nilsson e Riedel 10ª Edição

<iframe src="https://diegoascanio.github.io/jupyterlite/lab?path=exemplo-7.1.ipynb" width=100% height=100%></iframe> 


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33">

<div class="grid-element normal">

- Recapitulando: a resposta ao estímulo degrau (aplicação repentina de uma fonte de tensão / corrente) aos terminais de um passivo de armazenamento de energia representa a carga deste passivo.
- Uma vez que em \\(t = 0\\) a chave é ligada, logo, o capacitor \\(C\\) é conectado em paralelo ao equivalente de norton retratado, como visto na segunda imagem à direita.
- Estamos interessados em aprender como o capacitor se comporta em resposta ao estímulo degrau, ou seja, queremos saber como o capacitor carrega.
- Qual modelo matemático descreve este comportamento?
    - Será estudado agora!

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-degrau.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-degrau-circuito-equivalente.png)

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33">

<div class="grid-element regular">

- Ao analisar o circuito quando \\(t = 0\\) vemos que existem três correntes:
    1. \\(I_{S}\\), corrente constante oriunda da fonte de corrente;
    2. \\(I_{R}\\), corrente presente no resistor;
    3. \\(I_{C}\\), corrente de deslocamento presente no capacitor.

- Pela LKC nos nós temos que:
\\[
    I_{S} = I_{R} + I_{C}
\\]

**Queremos encontrar uma equação que nos permita calcular a tensão armazenada pelo capacitor ao longo do tempo — \\(V_{C}(t)\\) — em função da corrente \\(I_{S}\\) fornecida pela fonte de corrente.**

Porquê? Porquê a tensão é a grandeza de interesse do capacitor, é aquela a qual este elemento apresenta oposição à sua variação.

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-degrau.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-degrau-circuito-equivalente.png)

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33">

<div class="grid-element regular">


**Queremos encontrar uma equação que nos permita calcular a tensão armazenada pelo capacitor ao longo do tempo — \\(V_{C}(t)\\) — em função da corrente \\(I_{S}\\) fornecida pela fonte de corrente.**

- Pela LKC nos nós temos que:
\\[
    I_{S} = I_{R} + I_{C}
\\]

Sabemos que \\(I_{C} = C {{dV_{C}} \over {dt}}\\) e \\(I_{R} = {{V_{C}} \over R}\\). Logo:

\\[
C {{dV_{C}} \over {dt}} + {{V_{C}} \over R} = I_{S}
\\]

Pelo fato do termo a direita da EDO, \\(I_{S}\\), ser não nulo, estamos diante de uma EDO não-homogênea, que portanto, não pode ser resolvida com os métodos que abordamos até o momento. Felizmente, conseguimos obter nossa grandeza de interesse — \\(V_{C}(t)\\) — à partir do princípio da sobreposição linear.


</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-degrau.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-degrau-circuito-equivalente.png)

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33">

<div class="grid-element regular">

A tensão \\(V_{C}(t)\\) do capacitor em resposta ao degrau pode ser obtida sobrepondo-se a resposta forçada \\(V_{F}(t)\\) do capacitor com sua resposta ao estímulo natural \\(V_{N}(t)\\).

\\[
V_{C}(t) = V_{F}(t) + V_{N}(t)
\\]

- \\(V_{F}(t)\\) é a resposta forçada que ignora o armazenamento de energia do capacitor — desconsiderando o estado transitório — tendo em vista somente os estados permanentes do componente: **inicial (descarregado na resposta ao degrau) e em estabilidade (carregado na resposta ao degrau)**
- \\(V_{N}(t)\\) é a resposta natural do capacitor — durante o estado transitório num instante de tempo inicial \\(k\\) qualquer — que considera suas características de armazenamento (fornecimento) de energia.

Reiterando, em termos simples, a sobreposição garante que a tensão \\(V_{C}(t)\\) do capacitor pode ser calculada pela soma do seus comportamentos \\(V_{F}(t)\\) — no estado permanente — e \\(V_{N}(t)\\) — no estado transitório.

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-degrau.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-degrau-circuito-equivalente.png)

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33 regular">

<div class="grid-element">

### Cálculo da Resposta Forçada \\(V_{F}(t)\\)

A resposta forçada \\(V_{F}\\) desconsidera o estado transitório do sistema. Na resposta ao degrau, que como vimos, modela o comportamento de carga do capacitor, o capacitor no seu estado permanente — após a carga — apresenta a mesma tensão do equivalente de norton do circuito, ou seja:

\\[
V_{F}(t) = R \cdot I_{S}
\\]

### Cálculo da Resposta Natural \\(V_{N}(t)\\)

A resposta natural \\(V_{N}(t)\\) considera as características de armazenamento de energia do capacitor, portanto, como ele se comporta no estado transitório sob influência nula da fonte (tensão ou corrente) do sistema. Sabemos (como estudamos na resposta natural) que o circuito \\(RC\\) equivalente à resposta ao estímulo natural é como o mostrado pela segunda imagem à direita.

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-degrau-circuito-equivalente.png)

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-natural-circuito-equivalente.svg)

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

<div class="grid-66-33 regular">

<div class="grid-element">

### Cálculo da Resposta Natural \\(V_{N}(t)\\)

Neste circuito, pela LKC no nó A, temos que \\(I_{C} + I_{R} = 0\\). Podemos escrever \\(I_{C} \text{ e } I_{R}\\) em função da tensão de resposta natural \\(V_{N}(t)\\) num instante de tempo inicial \\(k\\) qualquer.

- \\(I_{C}\\), a corrente de deslocamento do capacitor, é \\( C {{dV_{N}} \over {dt}}\\);
- \\(I_{R}\\), a corrente do resistor, é \\({{V_{N}} \over R}\\).

Logo:

</div>

<div class="grid-element">

<!-- _class: transparent -->
![grid-img](./img/rc-resposta-natural-circuito-equivalente.svg)

</div>

</div>

<div class="grid-33-33-33 small">

<div class="grid-element">

\\[
\begin{align}
    &{C {{dV_{N}} \over {dt}}} + {{V_{N}} \over R} = 0 \therefore \\\\
    &{{dV_{N}} \over {V_{N}}} = -{{dt} \over {RC}} \therefore \\\\
    &\int_{k}^{t}{{{dV_{N}} \over {V_{N}}}} = - \int_{k}^{t}{{{dt} \over {RC}}} \therefore
\end{align}
\\]

</div>

<div class="grid-element">

\\[
\begin{align}
    &ln(V_{N}(t)) - ln(V_{N}(k)) = {{-t} \over {RC}} + {{k} \over {RC}} \therefore \\\\
    &ln({{V_{N}(t)} \over {V_{N}(k)}}) = {{-t} \over {RC}} + {{k} \over {RC}} \therefore \\\\
    &{{V_{N}(t)} \over {V_{N}(k)}} = e^{{{-t} \over {RC}} + {{k} \over {RC}}} \therefore \\\\
\end{align}
\\]

</div>

<div class="grid-element small">

\\[
\begin{align}
    & V_{N}(t) = V_{N}(k) \cdot e^{{{k} \over {RC}}} \cdot e^{{{-t} \over {RC}}} \\\\
    & \text{Considerando } V_{N}(k) \cdot e^{{{k} \over {RC}}} \text{ como } K_{N} \text{ temos que: } \\\\
\end{align}
\\]

<div class="normal" style="border-style: solid;">

\\[
\begin{align}
    & V_{N}(t) = K_{N} \cdot e^{{{-t} \over {RC}}} 
\end{align}
\\]

</div>

</div>

</div>


---

## Resposta ao Degrau do Circuito RC

### Cálculo da Resposta ao degrau \\((V_{C}(t))\\) pela sobreposição.

<div class="regular">

Como já encontramos \\(V_{F}(t)\\) e \\(V_{N}(t)\\), logo, conseguimos calcular \\(V_{C}(t)\\) pelo princípio da sobreposição. Assim:

\\[
\begin{align}
    V_{C}(t) &= V_{F}(t) + V_{N}(t) \therefore \\\\
    V_{C}(t) &= RI_{S} + K_{N}e^{{{-t} \over {RC}}} (I)
\end{align}
\\]

Como \\(K_{n}\\) representa a resposta natural a partir de um instante inicial de tempo \\(k\\) qualquer, para finalizar a resolução é necessário encontrar a resposta natural à partir do instante de tempo \\(t = 0\\).

Consideremos \\(V_{C}(0)\\):

\\[
\begin{align}
V_{C}(0) &= RI_{S} + K_{N} \cdot e^{{-0} \over {RC}} \\therefore \\\\
K_{N} &= V_{C}(0) - RI_{S}
\end{align}
\\]

Substituindo \\(K_{N}\\) em \\((I)\\), temos a equação que modela a resposta do cicuito \\(RC\\) ao degrau:

<div class="normal" style="border-style: solid;">

\\[
\begin{align}
V_{C}(t) = RI_{S} + (V_{C}(0) - RI_{S}) \cdot e^{{-t} \over {RC}}
\end{align}
\\]

</div>

</div>



---

## Determinação da Resposta ao Degrau de um Circuito RC
### Exemplo 7.6 Livro Nilsson e Riedel 10ª Edição

<iframe src="https://diegoascanio.github.io/jupyterlite/lab?path=exemplo-7.6.ipynb" width=100% height=100%></iframe> 

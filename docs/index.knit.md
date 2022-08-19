---
title: "Ensaios sobre novos modelos incondicionais e de regressão com implementação computacional"
subtitle: "TCC A"
author: "Caroline Cogo Carneosso <br> Orientador Prof. Thiago A. N. De Andrade <br> Coorientador Prof. Cleber Bisognin"
institute: "Universidade Federal de Santa Maria <br/> Departamento de Estatística"
format: 
    revealjs:
        theme: [solarized, custom.scss]
        preview-links: auto
        chalkboard: true
        transition: fade
        controls: true
        width: 1190
        height: 720
        bibliography: bib.bib
        nocite: |
          @*
---


## Sumário

::: {.incremental}

<br />

- Proposição de novas distribuições baseadas em geradores 
<br />

- A nova classe ERF-G e suas vantagens
<br />

- Novos modelos a serem explorados
<br />

- Erf-Weibull
<br />

- Resultados
<br />

- Bibliografia

:::







## Proposição de novas distribuições baseadas em geradores

1.**Exp-G**

<br />

- **Lehmann tipo I**


$$F(x)=G(x)^\alpha,$$  


<br />

- **Lehmann tipo II**


$$F(x)=1-\left[1-G(x)\right]^\alpha,$$


onde $\alpha>0$.


---

2.**EG-G**

<br />

@cordeiro2013exponentiated


$$F(x)=\left\{1-\left[1-G(x)\right]^\alpha\right\}^\beta.$$


onde $\alpha>0$ e $\beta>0$ são dois parâmetros adicionais de forma.

<br />

* Se $\alpha= 1$ temos **TL I**.
* Se $\beta= 1$ temos **TL II**.

---


3.**KW-G**

<br />

@cordeiro2011new


$$ F(x)=1-\left[1-G(x)^\alpha\right]^\beta. $$

onde $\alpha>0$ e $\beta>0$

<br />


* Se $\alpha= 1$ temos **TL II**.
* Se $\beta= 1$ temos **TL I**.


---

4.**Beta-G**

<br />

@eugene2002beta


$$F(x)=I_{G(x)}(a,b)=\frac{1}{B(a,b)}\int_0^{G(x)}w^{a-1}(1-w)^{b-1}dw$$


<br />

para $a>0$ e $b>0$, parâmetros que governam a assimetria e a curtose da distribuição, onde $I_{G(x)}(a,b)$ é a razão da função beta incompleta, e $B(a,b)=\Gamma (a)\Gamma (b)/\Gamma(a+b)$ é a função beta.

---


5.**Gamma-G**

@zografos2009families e @ristic2012gamma


$$ F(x)=\frac{\gamma\left( a, -\log \left[1-G(x)\right]\right)}{\Gamma(a)} =
\frac{1}{\Gamma(a)} \int_0^{-\log \left[1-G(x)\right]} t^{a-1} \exp (-t)dt.$$

<br />

para $a>0$, onde $\Gamma(a)=\int_0^\infty t^{a-1}\,\rm{e}^{-t}dt$ é a função gama
e $\gamma(a,z)=\int_0^{z} t^{a-1}\,\rm{e}^{-t}dt$ denota a função gama incompleta.

---

6.**Erf-G**


$$F(x)=\text{Erf}\left[\frac{G(x)}{1-G(x)}\right],$$



onde $G(x)$ é uma função de distribuição acumulada (fda).


## A nova classe ERF-G e suas vantagens

E recentemente, introduzida por  @fernandez2020erf, a família Erf-G.

A função erro é dada por 


$$\text{Erf}(z)=\frac{1}{\sqrt{\pi}}\int_{-z}^z \exp(-t^2)\, \textrm{d}t=\frac{2}{\sqrt{\pi}}\int_0^z \exp(-t^2) \,\textrm{d}t,\quad z \in \mathbb{R}.$$

$$F(x)=\text{Erf}\left[\frac{G(x)}{1-G(x)}\right],$$



---


![](logExp_Erf-Exp_plot1024_1.jpg){.absolute top=10 right=190 width="950" height="900"}


---

Seja $X\sim$ Erf-G $(\boldsymbol{\theta})$ for $\boldsymbol{\theta} \in \boldsymbol{\Theta} \subseteq \mathbb{R}^p$, where $\boldsymbol{\Theta}$ represents the parametric space. The pdf of $X$ and hrf are given by, respectively, (for $x \in \mathbb{R}$)



$$f(x)=\frac{2g(x;\boldsymbol{\theta})\exp\left[-\left(\dfrac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right)^2\right]}{\sqrt{\pi}(1-G(x;\boldsymbol{\theta}))^2}$$


and


$$h(x)=\frac{2g(x;\boldsymbol{\theta})\exp\left[-\left(\dfrac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right)^2\right]}{\sqrt{\pi}(1-G(x;\boldsymbol{\theta}))^2 \left\{  1-\text{Erf}\left[\frac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right]  \right\}}.$$



## Novos modelos a serem explorados

* Erf-Wei

<br />

* Erf-Normal

<br />

* Erf- Gamma

## Erf-Weibull

Função de distribuição acumulada 


$$F(x)=\text{Erf}\left[\exp\left(\alpha x^\beta\right)-1\right].$$


Função de densidade de probabilidade


$$f(x)=2\pi^{-1/2}\,\alpha\,\beta\, x^{\beta-1}\exp\left\{\alpha x^\beta-\left[\exp(\alpha x^\beta)-1\right]^2\right\}.$$


Função de taxa de falha 


$$h(x)=\dfrac{2\,\alpha\,\beta\, x^{\beta-1}\exp\left\{\alpha x^\beta-\left[\exp(\alpha x^\beta)-1\right]^2\right\}}{\sqrt{\pi}\left\{1-\text{Erf}\left[\exp(\alpha x^\beta)-1\right]\right\}}.$$


## Resultados 

* Pacote hospedado no Github 

<br />

::: {.cell}

```{.r .cell-code}
#devtools::install_github("https://github.com/AlissonRP/erfG")
```
:::


## {auto-animate="true"}

```r
# Talvez falar sobre uma distribuição, ai quando "passar" ele mostra o código de como é
output$phonePlot <- renderPlot({
  # Render a barplot
})
```

## {auto-animate=true}

```r
# look at this!
output$phonePlot <- renderPlot({
  # Render a barplot
  barplot(WorldPhones[,input$region]*1000, 
          main=input$region,
          ylab="Number of Telephones",
          xlab="Year")
})
```


# Obrigada pela atenção!

# Bibliografia






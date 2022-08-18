---
title: "Ensaios sobre novos modelos incondicionais e de regressão com implementação computacional"
subtitle: "TCC A"
author: "Caroline Cogo Carneosso <br> Orientador Prof. Thiago A. N. De Andrade"
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
        slide-tone: true

---



# Aproveita que é html pra colocar gif

![](https://64.media.tumblr.com/4e52164984f5108ecce07bea93c1c961/2895e2bf8d41633c-55/s640x960/d60b66abc5dd759588d0d514ff668802f7ad610d.gifv){.absolute top=190 left=150 width="350" height="858"}


## Sumário

::: {.incremental}
- Introdução

<br />

- Desenvolvimento


<br />

- Conclusões
:::







## Artigo

* Muda isso aqui por favor?

::: {.incremental}

* Faz uma introdução do problema sei lá

<br />

* :)

<br /> 
:::


## Proposição de novas distribuições baseadas em geradores

1.**Gamma-G**


$$ F(x)=\frac{\gamma\left( a, -\log \left[1-G(x)\right]\right)}{\Gamma(a)} =
\frac{1}{\Gamma(a)} \int_0^{-\log \left[1-G(x)\right]} t^{a-1} \exp (-t)dt.$$

para $a>0$, onde $\Gamma(a)=\int_0^\infty t^{a-1}\,\rm{e}^{-t}dt$ é a função gama
e $\gamma(a,z)=\int_0^{z} t^{a-1}\,\rm{e}^{-t}dt$ denota a função gama incompleta.


---

2.**EG-G**


---

3.**Beta-G**

---

4.**Exp-G**



$$F(x)=\left[1-\left\{1-G(x)\right\}^\alpha\right]^\beta.$$


onde $\alpha>0$ e $\beta>0$ são dois parâmetros adicionais de forma.

---

5.**Erf-G**


$$F(x)=\text{Erf}\left[\frac{G(x)}{1-G(x)}\right].$$



Onde $G(x)$ é uma função de distribuição acumulada (fda).


## A nova classe ERF-G e suas vantagens

E recentemente, introduzida por Zea e Andrade (2020), a família erf-G

A função erro é dada por 

\begin{equation}\label{erf}
\text{erf}(z)=\frac{1}{\sqrt{\pi}}\int_{-z}^z \exp(-t^2)\, \textrm{d}t=\frac{2}{\sqrt{\pi}}\int_0^z \exp(-t^2) \,\textrm{d}t,\quad z \in \mathbb{R}.
\end{equation}


## Equações

Now, let $X\sim$ erf-G $(\boldsymbol{\theta})$ for $\boldsymbol{\theta} \in \boldsymbol{\Theta} \subseteq \mathbb{R}^p$, where $\boldsymbol{\Theta}$ represents the parametric space. The pdf of $X$ and hrf are given by, respectively, (for $x \in \mathbb{R}$)



$$f(x)=\frac{2g(x;\boldsymbol{\theta})\exp\left[-\left(\dfrac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right)^2\right]}{\sqrt{\pi}(1-G(x;\boldsymbol{\theta}))^2}$$


and


$$h(x)=\frac{2g(x;\boldsymbol{\theta})\exp\left[-\left(\dfrac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right)^2\right]}{\sqrt{\pi}(1-G(x;\boldsymbol{\theta}))^2 \left\{  1-\text{erf}\left[\frac{G(x;\boldsymbol{\theta})}{1-G(x;\boldsymbol{\theta})}\right]  \right\}}.$$



## Novos modelos a serem explorados

* Erf-Wei

* Erf-Normal

* Erf-

## Erf-Weibull

Adding concavity in the likelihood of Weibull distribution: a new
model with bathtub hazard function

Função de distribuição acumulada 


$$F(x)=\text{Erf}\left[\exp\left(\alpha x^\beta\right)-1\right].$$


Função de densidade de probabilidade


$$f(x)=2\pi^{-1/2}\,\alpha\,\beta\, x^{\beta-1}\exp\left\{\alpha x^\beta-\left[\exp(\alpha x^\beta)-1\right]^2\right\}.$$


Função de taxa de falha 


$$h(x)=\dfrac{2\,\alpha\,\beta\, x^{\beta-1}\exp\left\{\alpha x^\beta-\left[\exp(\alpha x^\beta)-1\right]^2\right\}}{\sqrt{\pi}\left\{1-\text{Erf}\left[\exp(\alpha x^\beta)-1\right]\right\}}.$$


## Resultados aplicados

## pacote

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

* Apresentar uma aplicação

# Obrigada pela atenção!

oi, vc vem sempre por aqui?

![](https://fotos.vivadecora.com.br/decoracao-quarto-de-casal-tapete-creme-casacor2016-104905-square_cover_xlarge.jpg){.absolute top=190 left=150 width="650" height="858"}











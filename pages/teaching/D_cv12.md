---
layout: default
title: KKE/D - Cvičení 12
---

#### KME/D - Cvičení 12 
## Volné kmitání soustav s jedním stupněm volnosti

### Příklad 5: Těžní klec

Těžní klec o hmotnosti $m_2$ se pohybuje konstantní rychlostí $v_0$. Určete maximální sílu v&nbsp;ocelovém laně o hmotnosti $m_1$ a tuhosti $k_1$, jež vznikne při náhlém zastavení horního konce lana v bodě $A$. 
Vyšetřete pohyb těžní klece za předpokladu poměrného útlumu $D=0,2$. 
V&nbsp;jakém poměru se zmenší amplituda výchylky po dvou kmitech?

**Dáno:** 
$\;m_1 = 1,2 \cdot 10^4 \, \mathrm{kg}$, 
$\;m_2 = 2   \cdot 10^4 \, \mathrm{kg}$, 
$\;v_0 = 1              \, \mathrm{m/s}$, 
$\;k_1 = 1,5 \cdot 10^5 \, \mathrm{N\cdot m^{-1}}$,
$\;D = 0,2$

<img src="{{ 'figs/D_cv12/pr5.svg' | relative_url }}" class="image" style="width: 250px;">

---

Z předchozího již víme, že hmotnost pružného členu lze při sestavení vlastní pohybové rovnice ekvivalentně zohlednit tak, že k hmotnosti těžní klece přičteme třetinu hmotnosti lana, tedy

$$
m_c = m_2 + \frac{m_1}{3}.
$$

Zavedeme-li souřadnici $x(t)$ jako výchylku těžní klece od statické rovnovážné polohy, lze pohyb těžní klece popsat jako podélné kmitání soustavy s jedním stupněm volnosti, které je dáno následující homogenní lineární obyčejnou diferenciální rovnicí 2. řádu

$$
m_c\, \ddot{x} + b_c\, \dot{x} + k_c\, x = 0,
$$

kde $m_c$ označuje ekvivalentní hmotnost soustavy, $b_c$ je koeficient tlumení a $k_c$ je tuhost soustavy. Dále zavádíme **vlastní frekvenci** (netlumené) **soustavy** tak, že platí

$$
\frac{k_c}{m_c} = \Omega^2, \quad \frac{b_c}{m_c} = 2 D \Omega.
$$

V našem konkrétním případě je tuhost soustavy dána tuhostí pružného lana, tedy $k_c = k_1$. Po dosazení těchto výrazů do výše uvedené rovnice získáme následující počáteční úlohu pro výchylku těžní klece

$$
\left\{
\begin{aligned}
\ddot{x} + 2 D \Omega \dot{x} + \Omega^2 x &= 0, \\
x(0) &= 0, \\
\dot{x}(0) &= v_0.
\end{aligned}
\right.
$$

Pro nalezení obecného řešení sestavíme charakteristickou rovnici

$$
\lambda^2 + 2 D \Omega \lambda + \Omega^2 = 0,
$$

jejíž kořeny jsou

$$
\lambda_{1,2} = -D\Omega \pm  \Omega \sqrt{1 - D^2} \, \mathrm{i},
$$

Zavedeme nyní **vlastní frekvenci tlumené soustavy**

$$
\Omega_D = \Omega \sqrt{1 - D^2}.
$$

Protože pro zadaný poměrný útlum platí $D < 1$, mají kořeny charakteristické rovnice nenulovou imaginární část a obecné řešení lze zapsat ve tvaru tlumených harmonických kmitů s&nbsp;exponenciálním útlumem

$$ 
  x(t) = \mathrm{e}^{-D\Omega t} \bigl( A \cos (\Omega_D t) + B \sin (\Omega_D t) \bigr).
$$

Konstanty $A$ a $B$ určíme z počátečních podmínek. Derivací výrazu $x(t)$ získáváme

$$
\dot{x}(t) = \mathrm{e}^{-D\Omega t} 
              \Bigl(
              -D\Omega \bigl( A \cos(\Omega_D t) + B \sin(\Omega_D t) \bigr)
              + \Omega_D \bigl( -A \sin(\Omega_D t) + B \cos(\Omega_D t) \bigr)
              \Bigr).
$$

Z&nbsp;počáteční výchylky $x(0) = 0$ plyne $A = 0$. Dosazením do počáteční podmínky pro rychlost $\dot{x}(0) = v_0$ pak dostáváme $B = v_0 / \Omega_D$. Tím jsme získali explicitní vyjádření výchylky těžní klece ve tvaru

$$ 
  x(t) = \frac{ v_0 }{ \Omega_D } \mathrm{e}^{-D\Omega t} \sin (\Omega_D t),
$$

a odpovídající rychlosti

$$ 
  \dot{x}(t) = \frac{ v_0 }{ \Omega_D } \mathrm{e}^{-D\Omega t}  \bigl( -D\Omega \sin (\Omega_D t) + \Omega_D \cos (\Omega_D t) \bigr).
$$

![Težní klec]({{ 'gifs/pr5.gif' | relative_url }})

**Maximální síla v ocelovém laně** bude vznikat v bodě $A$, kde je lano zatíženo tíhovou silou klece, tíhovou silou celého lana a silou v pružném laně vyvolanou jeho maximálním prodloužením, tj.

$$
  F_{\mathrm{max}} = \left( m_1 + m_2 \right) g + k_1 x_{\mathrm{max}}.
$$

Tato síla nastává v okamžiku, kdy je výchylka těžní klece maximální, a tedy její rychlost je nulová, tj. $\dot{x}(t) = 0$.  Z&nbsp;výše uvedeného výrazu pro rychlost těžní klece roto získáme podmínku pro čas $t_\mathrm{max}$, v němž maximální síla nastává. Protože konstanta i exponenciální člen jsou pro $\forall t \geq 0$ , musí být splněna rovnost

$$
-D\Omega \sin (\Omega_D t) + \Omega_D \cos (\Omega_D t) = 0,
$$

a tedy

$$
 \mathrm{tg} (\Omega_D t) = \frac{\Omega_D}{D\Omega}.
$$

Tato rovnost je splněna pro časy

$$
  t_j = \frac{1}{\Omega_D} \arctan \left( \frac{\Omega_D}{D\Omega} \right) + j \frac{\pi}{\Omega_D}, \quad j = 0, 1, 2, \ldots
$$

Maximální výchylce těžní klece zřejmě odpovídá první z těchto hodnot, tedy pro $j=0$,

$$
  t_\mathrm{max} = \frac{1}{\Omega_D} \arctan \left( \frac{\Omega_D}{D\Omega} \right),
$$

a proto je dána vztahem

$$
  x(t_\mathrm{max}) \equiv
  x_\mathrm{max} = \frac{ v_0 }{ \Omega_D } \mathrm{e}^{-D\Omega t_\mathrm{max}} \sin (\Omega_D t_\mathrm{max}).
$$

Pro nalezení **poměru amplitud po dvou kmitech** vyjdeme z výrazu pro výchylku těžní klece. Označíme-li periodu tlumeného kmitání symbolem $T_D = 2\pi / \Omega_D$, platí

$$
\begin{aligned}
  \frac{x(t)}{x(t + 2T_D)} &= \frac{ \frac{ v_0 }{ \Omega_D } \mathrm{e}^{-D\Omega t} \sin (\Omega_D t) }
                                   { \frac{ v_0 }{ \Omega_D } \mathrm{e}^{-D\Omega (t + 2T_D)} \sin (\Omega_D (t + 2T_D)) } \\
                           &= \frac{ \mathrm{e}^{-D\Omega t} }
                                   { \mathrm{e}^{-D\Omega (t + 2T_D)} } \\
                           &= \frac{ \mathrm{e}^{-D\Omega t} }
                                   { \mathrm{e}^{-D\Omega t } \mathrm{e}^{-D\Omega 2T_D}} \\
                           &= \mathrm{e}^{2D\Omega T_D} \\
                           &= \mathrm{e}^{\frac{4 \pi D}{\sqrt{1 - D^2}}} \approx 13.
\end{aligned}                                 
$$

Amplituda výchylky se tedy po dvou kmitech zmenší přibližně třináctkrát.
# Introducción a los SAI

## ¿Qué es un SAI?

## ¿Qué tipos existen?

## ¿Cómo funcionan?

## Cálculos de SAI
**Este es un ejemplo de ejercicio sobre calculos de SAI**

Este cálculo es acorde a la situación que me proponen:

$$(30 \cdot 200) + (30 - 30) + 400 + 900 = 6000 + 900 + 400 = 7300 \, W$$

El siguiente cálculo es con los dispositivos que yo he escogido:

$$(30 \cdot 90) + (35 - 30) + 436 = 2700 + 500 + 436 = 4186 \, W$$

Para los VA asumiré que el factor de potencia es 1:

$$VA = \frac{W}{FP}$$

Donde $FP$ es el factor de potencia y $W$ son los vatios.

El factor de potencia se puede evaluar de 2 maneras:

1. **Primera forma:**

   $$FP = \frac{P}{S}$$

   a. Donde $P$ es la potencia activa (W) y $S$ son los VA.

2. **Segunda forma:**

   $$FP = \cos(\phi)$$

   a. Donde $\phi$ es el ángulo del triángulo, en mi caso tomaré que el ángulo es 30°:

   $$FP = \cos(30°) = 0.866$$

También para completar el triángulo completo, podemos añadir los VAR (Voltioamperios reactivos).

$$Q = \sqrt{S^2 - P^2} = \sqrt{(4833.71)^2 - (4185.99)^2} = \sqrt{23364752 - 17522152} = \sqrt{5842399} = 2417.07 \, VAR$$

$$VA = \frac{4186}{0.866} = 4833.71 \, VA$$

La fórmula $Q$ es literalmente el teorema de Pitágoras.

$$P = FP \cdot S = 4833.71 \cdot 0.866 = 4186 \, W$$

### AUTONOMÍAS

**Este es un ejemplo de ejercicio sobre el cálculo de autonomías**

CÁLCULOS AUTONOMÍA:

**SAI OFFLINE:**

$$
Autonomía = \left(\frac{N \cdot V \cdot Ah - Ef}{S}\right) \cdot 60
$$

$$
S = \frac{W}{FP} = \frac{4186}{0.866} = 4833.71 \, VA
$$

$$
FP = \cos(\phi) = \cos(30) = 0.866
$$

$$
T = \left(\frac{1.12 - 0.8}{4833.71}\right) \cdot 60 = \left(\frac{0.72}{4833.71}\right) \cdot 60 = 0.01 \cdot 60 = 0.83 \, mins
$$

---

**SAI LINE-INTERACTIVE:**

$$
Autonomía = \left(\frac{N \cdot V \cdot Ah - Ef}{S}\right) \cdot 60
$$

$$
S = \frac{W}{FP} = \frac{4186}{0.866} = 4833.71 \, VA
$$

$$
FP = \cos(\phi) = \cos(30°) = 0.866
$$

$$
Ef = 0.98
$$

$$
T = \left(\frac{1 - 0.12 - 0.98}{4833.71}\right) \cdot 60 = \left(\frac{0}{4833.71}\right) \cdot 60 = 0.02 \cdot 60 = 1.31 \, mins
$$

---

**SAI ONLINE:**

$$
Autonomía = \left(\frac{N \cdot V \cdot Ah - Ef}{S}\right) \cdot 60
$$

$$
S = \frac{W}{FP} = \frac{4186}{0.866} = 4833.71 \, VA
$$

$$
FP = \cos(\phi) = \cos(30°) = 0.866
$$

$$
T = \left(\frac{1.12 - 240 - 0.98}{2187.71}\right) \cdot 60
$$

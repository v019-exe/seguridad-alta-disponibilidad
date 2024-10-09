# Introducción a los SAI

## ¿Qué es un SAI?
El **Sistema de Alimentación Ininterrumpida (SAI)** es un dispositivo que proporciona energía eléctrica de respaldo a equipos y sistemas críticos en caso de un corte de energía o fluctuaciones en la red eléctrica. Su función principal es asegurar que los dispositivos conectados continúen funcionando sin interrupciones, protegiéndolos de apagones, picos de voltaje, caídas de tensión y otros problemas de calidad de la energía.

### Características Principales

- **Baterías de Respaldo**: Los SAI están equipados con baterías que se activan automáticamente cuando se detecta una pérdida de energía.
- **Regulación de Voltaje**: Muchos SAI también cuentan con sistemas de regulación que estabilizan el voltaje de salida, protegiendo así los equipos conectados.
- **Tiempo de Transferencia**: La mayoría de los SAI ofrecen un tiempo de transferencia rápido (en milisegundos) para minimizar cualquier interrupción en la energía.
- **Protección contra Sobrecargas**: Los SAI incluyen protecciones contra sobrecargas y cortocircuitos, lo que ayuda a evitar daños a los dispositivos conectados.

## ¿Qué tipos existen?
A continuación se muestran los diferentes tipos de SAI desde el más simple al mas avanzado:
### 1. SAI Offline (Standby)
- **Descripción**: Este es el tipo más básico de SAI. Funciona como un regulador de voltaje y proporciona energía de respaldo mediante baterías solo cuando hay un corte de energía.
- **Funcionamiento**: En condiciones normales, la energía eléctrica pasa directamente al equipo conectado. Cuando hay una interrupción, el SAI cambia rápidamente a la batería para mantener la energía.
- **Ventajas**: Costo relativamente bajo y fácil de instalar.
- **Desventajas**: Tiempo de transferencia entre la red y la batería puede afectar la continuidad de la operación.

### 2. SAI Line-Interactive
- **Descripción**: Este tipo de SAI ofrece características de regulación de voltaje adicional y es más sofisticado que el SAI offline.
- **Funcionamiento**: Utiliza un transformador para ajustar el voltaje y mejorar la calidad de la energía. Proporciona energía de respaldo durante un corte y puede regular el voltaje en condiciones de fluctuación.
- **Ventajas**: Proporciona una mejor protección contra sobrevoltajes y caídas de tensión.
- **Desventajas**: Generalmente más costoso que un SAI offline.

### 3. SAI Online (Doble Conversión)
- **Descripción**: Este es el tipo más avanzado de SAI. Convierte la energía de la red en corriente continua (DC) y luego la convierte nuevamente a corriente alterna (AC) para la salida.
- **Funcionamiento**: Proporciona una protección continua al equipo, ya que siempre está funcionando desde la batería, incluso cuando hay energía de la red disponible. Esto asegura una calidad de energía constante.
- **Ventajas**: Proporciona la mejor calidad de energía y protección contra todas las anomalías de la red eléctrica.
- **Desventajas**: Costo más alto y mayor consumo de energía en comparación con los otros tipos de SAI.

### 4. SAI Híbrido
- **Descripción**: Combina características de SAI offline y online. Puede cambiar entre el modo de funcionamiento de batería y el modo de línea.
- **Funcionamiento**: Dependiendo de la carga y las condiciones de la red, puede alternar entre los modos para optimizar la eficiencia y el tiempo de funcionamiento de la batería.
- **Ventajas**: Proporciona flexibilidad y eficiencia energética.
- **Desventajas**: Puede ser más complicado de gestionar y configurar.

### 5. SAI Modular
- **Descripción**: Este tipo de SAI permite la adición de módulos adicionales para aumentar la capacidad y la redundancia.
- **Funcionamiento**: Se pueden agregar o quitar módulos según las necesidades de energía, lo que permite una escalabilidad sencilla.
- **Ventajas**: Proporciona flexibilidad en la expansión del sistema según las demandas de energía.
- **Desventajas**: Generalmente más costoso y complejo que otros tipos.

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

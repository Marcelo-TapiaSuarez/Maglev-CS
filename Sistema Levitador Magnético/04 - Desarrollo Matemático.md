## Desarrollo Matemático para obtener la función de transferencia

La función no lineal representa la aceleración de la esfera despejada de la ecuación diferencial:

$$f(h, i) = \ddot{h} = g - \frac{\alpha}{m_b} \frac{i^2}{h^2}$$

Esta es una función escalar de dos variables independientes: $h$ (posición) e $i$ (corriente).

### 1. Evaluación en el punto de equilibrio

En el punto de operación $(\bar{h}, \bar{i})$, la aceleración debe ser cero ($\ddot{h} = 0$) porque la esfera está fija en levitación estática:

$$f(\bar{h}, \bar{i}) = g - \frac{\alpha}{m_b} \frac{\bar{i}^2}{\bar{h}^2} = 0$$

Tal como dedujiste, la imagen de la función en el punto es exactamente cero.

### 2. Desarrollo en Serie de Taylor multivariable de primer orden

El desarrollo de Taylor alrededor de $(\bar{h}, \bar{i})$ se formula como:

$$f(h, i) \approx f(\bar{h}, \bar{i}) + \left. \frac{\partial f}{\partial h} \right\vert_{(\bar{h}, \bar{i})} (h - \bar{h}) + \left. \frac{\partial f}{\partial i} \right\vert_{(\bar{h}, \bar{i})} (i - \bar{i})$$

Como $f(\bar{h}, \bar{i}) = 0$, el término constante desaparece y queda únicamente la combinación lineal de las derivadas parciales (el plano tangente):

$$f(h, i) \approx \left. \frac{\partial f}{\partial h} \right\vert_{(\bar{h}, \bar{i})} (h - \bar{h}) + \left. \frac{\partial f}{\partial i} \right\vert_{(\bar{h}, \bar{i})} (i - \bar{i})$$

### 3. Cálculo de las derivadas parciales evaluadas en el punto

**Derivada respecto a $h$:**

$$\frac{\partial f}{\partial h} = \frac{\partial}{\partial h} \left( g - \frac{\alpha}{m_b} i^2 h^{-2} \right) = 2 \frac{\alpha}{m_b} \frac{i^2}{h^3}$$

Evaluando en $(\bar{h}, \bar{i})$ y usando la igualdad del punto de equilibrio $\frac{\alpha}{m_b} \bar{i}^2 = g \bar{h}^2$:

$$\left. \frac{\partial f}{\partial h} \right\vert_{(\bar{h}, \bar{i})} = 2 \frac{g \bar{h}^2}{\bar{h}^3} = \frac{2g}{\bar{h}} = a_0(p)$$

**Derivada respecto a $i$:**

$$\frac{\partial f}{\partial i} = \frac{\partial}{\partial i} \left( g - \frac{\alpha}{m_b} \frac{i^2}{h^2} \right) = -2 \frac{\alpha}{m_b} \frac{i}{h^2}$$

Evaluando en $(\bar{h}, \bar{i})$ y sustituyendo $\bar{i} = \sqrt{\frac{m_b g}{\alpha}} \bar{h}$:

$$\left. \frac{\partial f}{\partial i} \right\vert_{(\bar{h}, \bar{i})} = -2 \frac{\alpha}{m_b \bar{h}^2} \left( \sqrt{\frac{m_b g}{\alpha}} \bar{h} \right) = -2 \frac{\sqrt{\frac{g \alpha}{m_b}}}{\bar{h}} = b_0(p)$$

### 4. Ecuación lineal final

Sustituyendo las derivadas en la aproximación de Taylor:

$$\ddot{h} \approx a_0(p)(h - \bar{h}) + b_0(p)(i - \bar{i})$$

Esta es exactamente la segunda fila de la ecuación de estados que aparece en la imagen:

$$\dot{x} = A(p)(x - x_0(p)) + B(p)(u - u_0(p))$$

Donde:

* $(h - \bar{h})$ es el término $(x_1 - x_{0,1})$.
* $(i - \bar{i})$ es el término $(u - u_0)$.

La no linealidad cuadrática desaparece localmente porque se anula el término de orden cero y se desprecian los órdenes superiores (segundas derivadas en adelante), dejando un sistema lineal válido para variaciones pequeñas alrededor del punto $(\bar{h}, \bar{i})$.


### 5. Cómo se resuelve el Maglev con Control Clásico

La linealización que ya analizaste conduce directamente a la función de transferencia sin matrices:

De la serie de Taylor obtuviste la aceleración de la desviación:

$$\Delta \ddot{h}(t) = a_0 \Delta h(t) + b_0 \Delta i(t)$$

Aplicando la Transformada de Laplace con condiciones iniciales nulas:

$$s^2 \Delta H(s) = a_0 \Delta H(s) + b_0 \Delta I(s)$$

Agrupando los términos de posición:

$$(s^2 - a_0) \Delta H(s) = b_0 \Delta I(s)$$

Despejando la relación salida/entrada, obtienes la función de transferencia de la planta:  

$$G(s) = \frac{\Delta H(s)}{\Delta I(s)} = \frac{b_0}{s^2 - a_0}$$

#### Por qué encaja con lo que te piden

* **Orden manejable:** Es un sistema de segundo orden sencillo, con dos polos reales: uno estable en $-\sqrt{a_0}$ y uno inestable en $+\sqrt{a_0}$.

---
## Explicación de Símbolos en G(s)

Los símbolos delta ($\Delta$) representan variables de desviación o incremento respecto al punto de equilibrio:

$$\Delta h(t) = h(t) - \bar{h}$$

$$\Delta i(t) = i(t) - \bar{i}$$

Se utilizan en la función de transferencia por dos razones matemáticas fundamentales de la teoría de control clásico:

### 1. Cumplir la condición de condiciones iniciales nulas en Laplace

La definición formal de una función de transferencia es la relación entre la transformada de Laplace de la salida y la de la entrada, asumiendo todas las condiciones iniciales iguales a cero:

$$G(s) = \left. \frac{Y(s)}{U(s)} \right\vert_{\text{condiciones iniciales} = 0}$$

Si usaras las variables absolutas $h(t)$ e $i(t)$, en el estado de reposo inicial la posición no vale cero ($h(0) = \bar{h} \neq 0$) y la corriente tampoco ($i(0) = \bar{i} \neq 0$).

Al definir las variables como la resta respecto al equilibrio, en el instante inicial (antes de cualquier perturbación) la desviación es nula:

$$\Delta h(0) = \bar{h} - \bar{h} = 0$$

$$\Delta i(0) = \bar{i} - \bar{i} = 0$$

Esto permite aplicar la transformada de Laplace a las derivadas directamente como $\mathcal{L}\{\Delta \ddot{h}(t)\} = s^2 \Delta H(s)$, sin términos adicionales de condiciones iniciales.

### 2. Eliminar el valor constante de equilibrio

Al aplicar la aproximación lineal por Series de Taylor, la aceleración se expresó como:

$$\ddot{h}(t) \approx a_0 (h(t) - \bar{h}) + b_0 (i(t) - \bar{i})$$

Dado que $\bar{h}$ es una constante, su segunda derivada temporal es cero ($\ddot{\bar{h}} = 0$). Por lo tanto:

$$\Delta \ddot{h}(t) = \frac{d^2}{dt^2}(h(t) - \bar{h}) = \ddot{h}(t)$$

Sustituyendo directamente las diferencias por sus deltas:

$$\Delta \ddot{h}(t) = a_0 \Delta h(t) + b_0 \Delta i(t)$$

El delta indica que el modelo no predice la altura absoluta total de la esfera, sino cuánto se desplaza la esfera hacia arriba o hacia abajo respecto a su posición de equilibrio nominal $\bar{h}$ cuando la corriente varía un pequeño valor $\Delta i$ respecto a la corriente base $\bar{i}$.
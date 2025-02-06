# 04/02/2025 - Regresion Lineal

- Gauss presento las bases para la Regresion Lineal al tratar de observar el planeta enano Ceres.

Ejemplo de un Predictor:

## 1. Definición de \( \Phi(x) \)

\[
\Phi(x) = (1, x_1)
\]

Aquí, \( \Phi(x) \) es la representación del punto de entrada \( x_1 \) en un espacio aumentado:

- El **"1"** representa el **término de sesgo** (o intercepto).
- \( x_1 \) es la variable independiente.

Como matriz fila:

\[
\Phi(x) =
\begin{bmatrix}
1 & x_1
\end{bmatrix}
\]

## 2. Vector de parámetros \( W \)

\[
W = (w_0, w_1)
\]

Es un **vector columna** con los coeficientes del modelo:

\[
W =
\begin{bmatrix}
w_0 \\
w_1
\end{bmatrix}
\]

## 3. Modelo de Regresión Lineal

\[
H_w(x) = W \cdot \Phi(x)
\]

Expandiendo la multiplicación de matrices:

\[
H_w(x) =
\begin{bmatrix}
w_0 & w_1
\end{bmatrix}
\cdot
\begin{bmatrix}
1 \\
x_1
\end{bmatrix}
\]

\[
H_w(x) = w_0 \cdot 1 + w_1 \cdot x_1 = w_0 + w_1 x_1
\]

## 4. Ecuación final

\[
y = w_0 + w_1 x_1
\]

donde:
- \( w_0 \) es el **intercepto**.
- \( w_1 \) es la **pendiente** de la recta.

Este enfoque es útil para la implementación de **regresión lineal múltiple** y aprendizaje automático.

# 6/02/2025 - 

Para proyecto se usaran las bibliotecas 
- NumPy y Matplotlib
- Regresion Logistica
- Regularizacion(Opcional) 

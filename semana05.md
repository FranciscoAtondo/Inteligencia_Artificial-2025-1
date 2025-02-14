# 10/02/2025 - Regresion Lineal

x={x^(1), x^(2), x^(3), ... , x^(m)} C R^n

y={y^(1), y^(2), y^(3), ... , y^(m)} e {-1, 1}

x^(i) = (x_1^(i), ... , x_m^(i))

y^(1) = f(x^(i)) + e^(i)

n: R^n -> {-1, 1}, n e H tal que h^* = f

1 - Que es H?
2 - Como mido h = f?
3 - Como encuentro h^*?

### Para Clasificacion Lineal Binaria:
y = h_w (x) = sign(w_1 x_1 + w_2 x_2 + ... + w_n x_n + w_0)

H = { h_w | w e R^(n+1), h_w(x) = sign(sigma_j=1^n w_j x_j + w_0) }

sig(w_2 x_2 + w_n + x_n + w_0)

w_2 x_2 + w_1 x_1 + w_0

x_2 = (w_1)/(w_2) x_1 + (w_0)/(w_2) = m x_1 + b

y = {y^(1), y^(2), y^(3), ... , y^(m)}

y' = {y'^(1), y'^(2) ... , y'(m)}

0|1 - Loss (y, y') = {0 si y = y' o 1 en otro caso

P_r (y = 1 | x;w ) = a(x) = theta(w_1 x_1 + w_2 x_2 + ... + w_n x_n + w_0)

y = {1 si a(x) > C o -1 en otro caso

lim_z->-inf theta(z) = 0

lim_z->inf theta(z) = 1

theta estrictamente reciente

theta(z) = 1/(- + e^-z)

a(x) = [P_r (y^(1) = 1 | x^(1);w), P_r (y^(2) = 1 | x^(1);w), ... , P_r (y^(m) = 1 | x^(1);w)] = [y'^(1), y'^(2), ... , y'^(m)] [y^(1), y^(2), ... , y^(m)]

[si y^(i) = 1:
  loss( y^(i), y'^(i) ) = -log(y'^(i))

si y^(i) = 0:
  loss(y^(-i) , y'^(i)) = -log(1-y'^(i))]

} y^(i) log(y'^(i)) + (1 - y(i)) log(1-y' (i))

w^* = arg min_w e R^n+1 1/M sigma_i=1^M - y^(i) log(y'^(i)) - (1 - y(i)) log(1 - y'^(1) donde y'(i) = theta(z^(i)) = 1/(1+e^-z(i))

z(i) = w_1 x_1^(i) + w_2 x_2^(i) + ... + w_n x_n^(i) + w_0 = x^(i)T w + w_0

### Descenso de Gradiente:

Se busca encontrar el punto de W donde se minimice la perdida.

desc_grad(x, y, w_ini, b_ini, n, max_epoch, e_tol)

  w <- w_|n|

  b <- b_|n|
  
  para epoch de 1 a max_epoch:
  
    V'_w J(w) <- Calcilar Gradiente (x, y, w, b)
    
    (2-J(w))/2b <- Calcula Derivada (x, y, w, b)
    
    w <- w-n V'_w - J(w)
    
    b <- b - n (2 - J(w))/2b
    
    si ||V'_w - J(w)||_inf < e_tol:
      
      regresa w,b
  
  regresa w,b

# 11/02/2025 - Descenso de Gradiente

El algoritmo se puede dividir en los siguientes pasos:

* Inicialización:
Se definen los valores iniciales de w y 𝑏.

* Cálculo del Gradiente:
Se calcula el gradiente de la función de pérdida respecto a w y b.

* Actualización de los Parámetros:
Se ajustan los valores de 𝑤 y 𝑏 en la dirección del gradiente negativo.

* Criterio de Paro:
Si la magnitud del gradiente es menor que un umbral 𝑒_tol, el algoritmo se detiene.

Descenso de Gradiente:
  hist <- []
  
  w <- w_ini
  
  b <- b_ini
  
  Para epoch de 1 en max_epoch:

    V̄_w E_in <- calcula_gradiente(x, y, w, b)
    
    d/dx E_in <- calcula_gradiente(x, y, w, b)

    hist.append( calcula-E_in (x, y, w, b))

    w <- w-n V̄_w E_in

    if ||V̄_w E_in || < E_tal:
      break

    fin para

  regresa w, b

El código incluye la expresión de la derivada de la función de pérdida en un problema de clasificación binaria con función de pérdida logarítmica (Log Loss o Entropía Cruzada):

(Ƨ E_in)/(Ƨ w) = Ƨ/Ƨw 1/m E_(n=1)^M -y^(i) log(ȳ (i)) - (1-y^(i)) log(1-ȳ^(i))

= 1/m E_(i=1)^m (-(y^(i))/ȳ^(i))) (Ƨδ( z^(i))/d(z^(i))) (dz^(i))/d(z^(i)) = 

# 12/02/2025 - Problemas de Busqueda

Tipos de Problemas:
- Observables
- No Observables
- Parcialmente Observables/No Deterministas
- Estado Desconocido

Consisten de:
- Estado Espacio
- Modelo de Transicion
- Estado Inicial, Objetivo y Funcion de Costo
- Solucion

Ejemplo - Pacman:

s = { s_1, s_2, ... }

s = (p, t_1, ... , t_a)

p e { 0, ... , 8)

t_i e {0, 1} # |s| = 9 * 2^9

s = (p_1, ... , p_9) # |s| = 9 * 2^8

p_i e {0, 1, 2}

A = {a_1, ... , a_m} acciones legales.

Modelo = <acciones_legales, transicion, costo_local>

acciones_legales: s->p(A) acciones_legales(s)

transicion: s*a->s transicion(s, A) = s

costo_local: s*a -> R costo_local(s, a) = c

# 13/02/2025 - Modelo de Busqueda

class modeloBusqueda:
  
  def __init__(self, s, A):
  
    self.s = s[:]
    self.A = A[:]

  def acciones_legales(self, s):

    return self.A[:]

  def transicion(self, s, a):

    raise NotImplementedError('Programa flojito')

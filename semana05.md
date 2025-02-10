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

  Tarea: Derivada de [d sigma (z)]/dz = sigma(z) (1 - sigma(z))

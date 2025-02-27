
Un sistema con entrada unitaria tiene la siguiente función de transferencia
$$G(s)=\frac{1000(s+8)}{(s+7)(s+8)}$$
**Calcula las constantes de error para :$K_p,K_v,K_a$ y utiliza estas respuestas para calcular los errores en estado estable para las entradas, escalón, rampa y parábola**


$$e_{ss}=\lim_{ s \to 0 } \frac{s}{1+G(s)}·\frac{A}{s}$$
Escalon: 
$$K_p=\lim_{ s \to 0 } G(s)\implies e_{ss}=\frac{A}{1+K_p}$$
Rampa
$$K_v=\lim_{ s \to 0 } s(G(s)) \implies e_{ss}=\frac{A}{K_v}$$
Parábola
$$K_a=\lim_{ s \to 0 } s^2G(s)\implies e_{ss} =\frac{A}{K_a}$$

-- a)
$$K_p=\lim_{ s \to 0 } \frac{1000(s+8)}{(s+7)(s+9)}=\frac{8000}{63}$$
$$K_v=\lim_{ s \to 0 } \frac{1000s(s+8)}{(s+7)(s+9)}=0$$
$$K_a=\lim_{ s \to 0 } \frac{1000s^2(s+8)}{(s+7)(s+9)}=0$$


-- b)
$$e_{ss}=\frac{A}{1+\frac{8000}{63}}=\frac{63A}{8063}=0.008A$$
$$e_{ss}=\frac{A}{0}=\infty$$
$$e_{ss}=\frac{A}{0}=\infty$$
Algo más podemos hacer pero no escuché ni entendí


# Ejercicio 2
Para las siguientes funciones de transferencia
--
$$G(s)=\frac{400}{s^2+12s+400}$$
$$G(s)=\frac{625}{s^2+9}$$
$$G(s)=\frac{900}{s^2+90s+900}$$
Calcula el error en estado estacionario para una entrada escalón
--

Para una entrada escalón, el error en estado estacionario se calcula con:
$$e_{ss}=\lim_{ s \to 0 } \frac{s}{1+G(s)H(s)}·\frac{A}{s}=\lim_{ s \to 0 } \frac{A}{1+G(s)H(s)}=\frac{A}{1+G(0)H(0)}$$

a) $G(s)=\frac{400}{s^2+12s+400}$
$$K_p=\lim_{ s \to 0 } \frac{400}{s^2+12s+400}=1$$
$$e_{ss}=\frac{A}{2}$$

b) $G(s)=\frac{625}{s^2+9}$
$$K_p=\lim_{ s \to 0 } \frac{625}{s^2+9}=\frac{625}{9}≈69.44$$
$$e_{ss}=\frac{A}{1+\frac{625}{9}}≈0.0142A$$

c) $G(s)=\frac{900}{s^2+90s+900}$
$$K_p=\lim_{ s \to 0 } \frac{900}{s^2+90s+900}=1$$
$$e_{ss}=\frac{A}{2}$$

Un escalón se puede convertir en rampa???????? wtf????????????saquenme de aqui?????????por favor????????????

# <span style="color:#ff0000">Ya me quiero ir a la verga</span> 

Para el sistema con retroalimentación unitaria donde $G(s)=\frac{450(s+8)(s+12)(s+15)}{s(s+38)(s^2+25s+28)}$
Calcula los errores en estado estable para las entradas
a) $25u(t)$
b) $37tu(t)$
c) $47t^2u(t)$

Se calcula la transformada a esa funcion y luego te <span style="color:#ff0000">suicidas</span> 
--
a)

$\mathscr{L}\{ 25u(t) \}=\frac{25}{s}$
Dado que $\frac{A}{s}=\frac{25}{s}$, $A=25$
$\therefore e_{ss}=\lim_{ s \to 0 }\frac{s}{1+G(s)}·\frac{25}{s}=0$
Usé wolfram

b) Wey que hueva sé que sí puedo pero ya qué hueva

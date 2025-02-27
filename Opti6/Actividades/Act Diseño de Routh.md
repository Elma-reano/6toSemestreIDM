
1. $$T(s)=\frac{k(s+1)}{s^4+2s^3+2s^2+(3+k)s+k}$$

| $s^4$ | $1$                     | $2$   | $k$ |
| ----- | ----------------------- | ----- | --- |
| $s^3$ | $2$                     | $3+k$ | $0$ |
| $s^2$ | $\frac{1-k}{2}$         | $k$   | $0$ |
| $s^1$ | $\frac{-k^2-6k+3}{1-k}$ | 0     | 0   |
| $s^0$ | k                       | 0     | 0   |

<span style="color:#0070c0">Intervalos</span>

(1) $k>0$
(2) $3+k>0\implies k>-3$
(3) $1-k>0\implies k<1$
(4) $\frac{-k^2-6k+3}{1-k}>0\implies -k^2-6k+3>0\implies-3-2\sqrt{ 3 }<k<-3+2\sqrt{ 3 }$

![[Act Diseño de Routh 2024-04-11 20.12.45.excalidraw]]


$\implies \text{Rango estabilidad}:0<k<-3+2\sqrt{ 3 }$

<div style="page-break-after: always;">--------</div> 


2. $$T(s)=\frac{k}{(s^2+s+1)(s+2)}$$
$$T(s)=\left[\frac{k}{(s^2+s+1)(s^2)}\right]\backslash\left[1+\frac{k}{(s^2+s+1)(s+2)}\right]$$
$$=\frac{k}{(s^2+s+1)(s+2)+k}=\frac{k}{s^3+3s^2+3s+(2+k)}$$

| $s^3$ | $1$                    | $3$   |
| ----- | ---------------------- | ----- |
| $s^2$ | $3$                    | $k+2$ |
| $s^1$ | $\frac{7-k}{3}$        | 0     |
| $s^0$ | $\frac{-k^2+5k+14}{3}$ | 0     |
<span style="color:#0070c0">Intervalos</span>

(1) $k+2>0\implies k>-2$
(2) $\frac{7-k}{(3)}>0\implies 7-k>0\implies k<7$
(3) $\frac{-k^2+5k+14}{3}>0\implies-2<k<7$

![[Act Diseño de Routh 2024-04-11 22.20.55.excalidraw]]

Rango de estabilidad: $-2<k<7$
<div style="page-break-after: always;"></div>


3. $$T(s)=\frac{k}{(s^2+8s+9)(s)}$$
$$T(s)=\left[\frac{k}{(s^2+8s+9)s}\right]\backslash\left[1+\frac{k}{(s^2+8s+9)s}\right]$$
$$=\frac{k}{s^3+8s^2+9s+k}$$

| $s^3$ | $1$             | $9$ |
| ----- | --------------- | --- |
| $s^2$ | $8$             | $k$ |
| $s^1$ | $9-\frac{k}{8}$ | 0   |
| $s^0$ | k               | 0   |

<span style="color:#0070c0">Intervalos</span>

(1) $k>0$
(2) $9-\frac{k}{8}>0\implies \frac{k}{8}<9\implies k<72$

![[Act Diseño de Routh 2024-04-11 22.19.12.excalidraw]]

Rango de estabilidad: $0<k<72$
<div style="page-break-after: always;"></div>


4. $$T(s)=\frac{k}{s(s^3+4s^2+10s)+20}$$
$$\frac{\left( \frac{k}{s^4+4s^3+10s^2+20} \right)}{1+\frac{k}{s^4+4s^3+10s^2+20}}=\frac{ \frac{k}{s^4+4s^3+10s^2+20}}{\frac{s^4+4s^3+10s^2+20+k}{s^4+4s^3+10s^2+20}}$$
$$=\frac{k}{s^4+4s^3+10s^2+20+k}$$

| $s^4$ | $1$               | $10$   | $20+k$ |
| ----- | ----------------- | ------ | ------ |
| $s^3$ | 4                 | 0      | 0      |
| $s^2$ | $10$              | $20+k$ | $0$    |
| $s^1$ | $-8-\frac{2k}{5}$ | 0      | 0      |
| $s^0$ | $20+k$            | 0      | 0      |
<span style="color:#0070c0">Intervalos</span>

(1) $20+k>0\implies k>-20$
(2) $-8-\frac{2k}{5}=\frac{-40-2k}{5}>0\implies-40-2k>0\implies 2k<-40\implies k<-20$

![[Act Diseño de Routh 2024-04-11 22.42.07.excalidraw]]

No existe un rango de estabilidad

<div style="page-break-after: always;"></div>


5. $$T(s)=\frac{k(s^2+2s+5)}{s(s^2+1)}$$
$$\frac{ \frac{k(s^2+2s+5)}{s(s^2+1)}}{1+\frac{k(s^2+2s+5)}{s(s^2+1)}}=\frac{ \frac{k(s^2+2s+5)}{s(s^2+1)}}{\frac{s(s^2+1)+k(s^2+2s+5)}{s(s^2+1)}}$$
$$=\frac{k(s^2+2s+5)}{s^3+s+ks^2+2ks+5k}=\frac{k(s^2+2s+5)}{s^3+ks^2+(2k+1)s+5k}$$

| $s^3$ | $1$     | $1+2k$ |
| ----- | ------- | ------ |
| $s^2$ | $k$     | $5k$   |
| $s^1$ | $-4+2k$ | $0$    |
| $s^0$ | $5k$    | 0      |
<span style="color:#0070c0">Intervalos</span> 

(1) $1+2k>0\implies k>-\frac{1}{2}$
(2) $k>0$
(3) $5k>0\implies k>0$
(4) $-4+2k>0\implies 2k>4\implies k>2$

![[Act Diseño de Routh 2024-04-11 22.52.24.excalidraw]]

Rango de estabilidad: $k>2$

-------------
<div style="page-break-after: always;"></div>


# Sección Matlab

## Comprobación 1

![[Pasted image 20240411230204.png]]
![[Pasted image 20240411230209.png]]
![[Pasted image 20240411230214.png]]
![[Pasted image 20240411230219.png]]
![[Pasted image 20240411230223.png]]
![[Pasted image 20240411230229.png]]
![[Pasted image 20240411230236.png]]
![[Pasted image 20240411230243.png]]

<div style="page-break-after: always;"></div>


## Comprobación 2

![[Pasted image 20240411230253.png]]
![[Pasted image 20240411230259.png]]
![[Pasted image 20240411230304.png]]
![[Pasted image 20240411230308.png]]
![[Pasted image 20240411230313.png]]
![[Pasted image 20240411230316.png]]
![[Pasted image 20240411230321.png]]
![[Pasted image 20240411230326.png]]
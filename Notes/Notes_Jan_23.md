# Jan 23 2026
## Backround
---

```
--------*-D-O----y[n]
        |   |
x[n]    Z1  |
        |-D-O
        |   |
x[n-1]  Z1  |
        |-D-O
        |   |
x[n-2]  Z1  |
x[n-3]  |-D-O

 ```
 For this we would want to store the output in a volatile RAM chip.

| Ram |    | Rom |
|-----|----|-----|
| x_0 | 00 | b_0 |
| x-1 | 01 | b_1 |
| x-2 | 10 | b_2 |
| x-3 | 11 | b_3 |

The code given converts

```
grab a/d --> memory
start:
get memx * get mem b
+previous
goto start
```
At n + 1 for example, you don't need x-3, but then you need to shift or use a circular addressing agorithm (simalar to wear leveling algorithm). USE POINTERS! (yay).

Interests:
- Finding coefficents (b)
- Hardware awareness

Some Desires DSP:
- Need memory
- multiply and add (MAC)
- Speed
- Input and output
- Efficient addressing (maybe circular addressing)
- Have the ability to debug or at least quantify outputs.

Look at block processing. Look at 256 point FFT. While doing that processing collect while measuring. So block processing seems to use grouping. There are optimal proceesses, no one size fits all tool.

```

---[a/d]---[DSP]---[D/C]---
x(t)    x[n]    y[n]    y(t)
```
All parts are important for DSP.
## Review

read ch 1.

ct signal models
u(t) = { 1 , t > 0 ; 1/2 , t=0; 0, t > 0
{PI}(t)  = {
y_total(t) = y_zir(t) + y_zsr(t)
really look at BiBo stability to refresh.
causality; h(t) = 0, t > 0

look at eigensignals

e^(st) --> [H] --> H(s) e^(st)

sinc = sin(pi*t) / (pi*t)

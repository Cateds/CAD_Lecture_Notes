# Lecture 11 : Inductors

> 所以这种大物里已经讲过的内容为什么还得放在CAD里再讲一遍，
> 莫名其妙的。

## Inductors（电感器）

### 电感的定义

电感是一种储能元件，可以在电流经过时储存能量，然后在电流停止时释放能量。它储存能量的方式是通过磁场。一个常见的电感由一个线圈组成，线圈的磁场会储存能量。

对于一个螺线管，可以通过实验得到这样的式子：

$$
N\Phi = LI
$$

这个式子是电感的定义式。

而对于一个长螺线管，可以得到：

$$
B = \frac{\mu_0 NI}{l}
$$

带入可以得到（ 这里的 $n$ 是每单位长度的匝数，即有 $n=\frac{N}{l}$ ）:

$$
N\Phi = \frac{N\cdot\mu_0 NIS}{l} = \mu_0 n^2 I \cdot V
$$

$$
L = \mu_0 n^2 Sl
$$

这样得出的式子就是电感的决定式。它的单位是亨利（H）。它说明了一个电感的电感量和它的几何形状有关，和线圈的密度有关，和材料的磁导率有关。

### 电感的UI关系

对它的定义式，通过法拉第电磁感应定律, 可得：

$$
\varepsilon = -N\frac{d\Phi}{dt} = -L\frac{dI}{dt}
$$

这里 $\varepsilon$ 是感应电动势， $L$ 是电感， $I$ 是电流。这个式子说明了电感产生的感应电动势的大小和电流的变化率有关。换句话说，电感会阻碍电流的变化。

同理，上述式子也可以写成积分形式

$$
\frac{1}{L}\cdot\int_{-\infty}^t\varepsilon dt = i(t)
$$

在电感上消耗的功率是：

$$
p(t) = i(t)\cdot\varepsilon = i(t)\cdot L\frac{di(t)}{dt}
$$

它储存的能量是：

$$
w(t) = \int_{-\infty}^t p(\tau)d\tau = \frac{1}{2}Li^2
$$

### 给电感通入交流信号

如果给电感通入一个正弦信号 $v(t) = Acos(\omega t)$ ，则电感上的电流有：

$$
i(t) = \frac{1}{L}\cdot\int_0^t v(\tau)d\tau = \frac{A}{L\omega}sin(\omega t) = \frac{A}{L\omega}cos(\omega t - \frac{\pi}{2})
$$

可以发现，最终得到的电流和电压之间的相位差是 $\frac{\pi}{2}$ ，并且电流的相位比电压的相位要领先。

两者的幅值之比是 $L\omega$ 。这说明电感的阻抗与通过其的电流频率成正比，即 $Z_L = j\omega L$ 。通过其的信号频率越高，电感的阻抗越大，最终导致电流的幅值越小。

同样的，如果我们通入变化的电流 $i(t) = A\cos(\omega t)$ ，则电感上的电压是：

$$
v(t) = L\frac{di(t)}{dt} = -LA\omega\sin(\omega t) = LA\omega\cos(\omega t + \frac{\pi}{2})
$$

结论和之前的保持一致。

## Series and Parallel Connection of Inductors（电感器的串联和并联）

> 仍然是在Physics II中学过的内容。
> 
> 进行一个PPT的搬运。

在电感串联时，通过其的电流是相同的，因此有

$$
N_1\Phi_1+N_2\Phi_2+\dots = L'I = L_1I + L_2I + \dots \\
\Rightarrow L' = L_1 + L_2 + \dots
$$

通过其定义式也能得到这个结论。

$$
V' = V_1 + V_2 + \dots = (L_1+L_2+\dots)\frac{di}{dt} = L'\frac{di}{dt} \\
\Rightarrow L' = L_1 + L_2 + \dots
$$

在电感并联时，类似的，可以得到他们两端的电压相同而通过其的电流不同. 已知对于一个电感， $i(t)=\frac{1}{L}\int_0^t v(\tau)d\tau$ ，所以

$$
i' = i_1 + i_2 + \dots = \frac{1}{L_1}\int_0^t v_1(\tau)d\tau + \frac{1}{L_2}\int_0^t v_2(\tau)d\tau + \dots \\
\Rightarrow \frac{1}{L'} = \frac{1}{L_1} + \frac{1}{L_2} + \dots    \\
\Rightarrow L' = \frac{1}{\frac{1}{L_1} + \frac{1}{L_2} + \dots}
$$
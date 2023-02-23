# 四元数

## 满足分配律，结合律，不满足结合律

## 乘法
$$\begin{aligned}
	p\otimes q &=
	\left[
	\begin{matrix}
		p_w q_w-p_x q_x-p_y q_y-p_z q_z \\
		p_w q_x+p_x q_w+p_y q_z-p_z q_y \\ 
		p_w q_y-p_x q_z+p_y q_w+p_z q_x \\
		p_w q_z+p_x q_y-p_y q_x+p_z q_w
	\end{matrix}
	\right] \\
	&=
	\left[
	\begin{matrix}
		p_w q_w - p_v^T q_v \\
		p_w q_v + q_w p_v + p_v \times q_v
	\end{matrix}
	\right] \\
	&=[p]_L\cdot q \\
	&=[q]_R\cdot p \\
\end{aligned}$$

$$\begin{aligned}
	[q]_L &= q_w \times I + 
	\left[
		\begin{matrix}
			0 & -q_v^T \\
			q_v & [q_v]_\times
		\end{matrix}
	\right] \\

	[q]_R &= q_w \times I + 
	\left[
		\begin{matrix}
			0 & -q_v^T \\
			q_v & -[q_v]_\times
		\end{matrix}
	\right]
\end{aligned}$$

$$
	[q_v]_\times \overset{\triangle}{=}
	\left[\begin{matrix}
		0 & -q_z & q_y \\
		q_z & 0 & -q_x \\
		-q_y & q_x & 0
	\end{matrix}\right]
$$

$$
	[p]_R[q]_L = [q]_L[p]_R
$$

## 恒等(identity)四元数
$$
	q_1 = 1 = \left[\begin{matrix}
		1 \\
		0_v
	\end{matrix}\right]
$$

## 共轭 
$q^*=\left[\begin{matrix}
	w \\
	-v
\end{matrix}\right]$

$$
q \otimes q^* = q^* \otimes q = \left[\begin{matrix}
	w^2+v^2 \\
	0_v
\end{matrix}\right] \\
(p\otimes q)^* = q^*\otimes p^*
$$

## 范数
$\|q\| = \sqrt{q \otimes q^*}$
$$\begin{aligned}
	\|p\|\otimes\|q\| &= \|p\otimes q\| \\
	&= \|p\| \|q\|
\end{aligned}$$

## 逆
$q\otimes q^{-1} = q^{-1}\otimes q = q_1$
$$
	q^{-1} = \frac{q^*}{\|q\|^2}
$$

## 单位(unit)\标准化(normalized)四元数
$\|q\| = 1$
$$q^{-1} = q^*$$
$$
	q = \left[\begin{matrix}
		\cos(\theta) \\
		u \sin(\theta)
	\end{matrix}\right]
$$

## 额外运算属性
* 交换子(commutator)
$$
	[p,q] = p\otimes q - q\otimes p = 2 p_v \times q_v
$$
* 纯四元数的乘法
$$\begin{aligned}
	p_v\otimes q_v &= -p_v^T q_v + p_v \otimes q_v \\
	&= \left[\begin{matrix}
		-p_v^T q_v \\
		p_v\otimes q_v
	\end{matrix}\right] 
\end{aligned}$$
$$q_v\otimes q_v = -q_v^T q_v = -\|q_v\|^2$$
* 单位纯四元数

$u\otimes u = -1$，类比于$i\cdot i=-1$

* 纯四元数的自然幂次

设$v=u\theta,\theta = \|v\|$,u是单位四元数
$$v^2=-\theta^2,v^3=-u\theta^3,v^4=\theta^4,v^5=u\theta^5,v^6=-\theta^6$$

* 纯四元数的幂指数

按幂级数的方法类比定义$e^v = \sum_{k=0}^{\infty}\frac{1}{k!}v^k\in H$,让$v=u\theta,\theta=\|v\|\in R,u$是单位纯四元数，则
$$e^v=e^{u\theta}=cos\theta +u sin\theta=\left[\begin{matrix}
cos\theta \\
u sin\theta
\end{matrix}\right]$$
$$
e^-v = (e^v)^*
$$
当$\theta$很小时
$$\begin{aligned}
e^v &\approx \left[\begin{matrix}
	1-\theta^2/2 \\
	v(1-\theta^2/6)
\end{matrix}\right] \\
&\approx \left[\begin{matrix}
	1 \\
	v
\end{matrix}\right] \\
&\approx \left[\begin{matrix}
	1 \\
	0
\end{matrix}\right]
\end{aligned}$$

* 单位四元数对数$\|q\|=1$
$$\begin{aligned}
	\ln q &= ln(cos\theta +u sin\theta) \\
	&= ln(e^{u\theta}) \\
	&= u\theta \\
	&= \left[\begin{matrix}
		0 \\
		u\theta
	\end{matrix}\right]
\end{aligned}$$
其中$u=q_v/\|q_v\|,\theta=arctan(\|q_v\|,q_w)$
$$\begin{aligned}
	\ln q &\approx \frac{q_v}{q_w}\left(1-\frac{\|q_v\|^2}{3q_w^2}\right) \\
	&\approx 0
\end{aligned}$$

* 一般四元数对数
$$\begin{aligned}
	\ln q &\approx\left[\begin{matrix}
		ln\|q_v\| \\
		u\theta
	\end{matrix}\right]
\end{aligned}$$

* 指数
$$
q^t = \left[\begin{matrix}
\cos t\theta \\
u \sin t\theta
\end{matrix}\right]
$$
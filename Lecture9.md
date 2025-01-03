# Lecture 9 : Norton's Theorem & Maximum Power Transfer Theorem

## Norton's Theorem（诺顿定理）

诺顿定理（Norton's Theorem）是电路分析中的一个重要定理，它可以将一个线性电路简化为一个等效的诺顿电路。这个等效的诺顿电路由两部分组成：一个等效的电流源和一个等效的电阻。

诺顿定理与戴维南定理的区别在于，戴维南定理将电路简化为一个等效的电压源和一个等效的电阻，而诺顿定理将电路简化为一个等效的电流源和一个等效的电阻。而根据电源的等效性，这两种等效电路是等效的。

类似的，我们可以通过测量开路电压和短路电流来求解等效电路的参数。在这种情况下，电流源的电流大小即为短路电流的大小，其电阻的阻值为开路电压与短路电流的比值。

需要注意的是，这种等效仍然是对外的等效，对内部并不能等效。也就是说，这个二端口网络消耗的功率和这个等效电路并不一定相同。

同样需要注意的是，如果我们把压降的方向视为电压源的方向，电流的方向视为电流源的方向，那么在进行源变换的时候，电压源的方向和电流源的方向是相反的。此处也是一样的。

我们也可以通过戴维南定理部分提到的类似的三种方法来求得等效电阻。

## Maximum Power Transfer Theorem（最大功率传输定理）

最大电阻功率定理（Maximum Power Transfer Theorem）是电路分析中的一个重要定理，它指出在一个线性电路中，当负载电阻等于电路的等效电阻时，电路传输到负载电阻的功率最大。

加入我们以 $R_L$ 为负载电阻， $R_{th}$ 为电路的等效电阻， $V_{th}$ 为电路的等效电压， $I_{th}$ 为电路的等效电流，那么负载电阻上的功率为：

$$
P = I_L^2 \cdot R_L = \left( \frac{V_{th}}{R_L + R_{th}} \right)^2 \cdot R_L
$$

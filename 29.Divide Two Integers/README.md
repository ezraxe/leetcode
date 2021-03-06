
### 方法一

循环递减，每次减去除数，直到小于除数，记录次数

效率低，时间开销大

### 方法二

如果被除数比除数的2倍大，则将除数变为当前值的2倍（因此，次数也成倍增加），直到被除数小于除数的2倍。然后将被除数减去除数，处理剩下的值，例如被除数为15，除数为2，有下列过程：

* 15大于2，因此初始化计数为1
* 由于15大于4(2<<1)，那么15里面肯定包含2个2，计数翻倍，变为2
* 由于15大于8(4<<1)，那么15里面肯定包含4个2，计数翻倍，变为4
* 由于15小于16(8<<1)，说明15不可能包含8个2，因此15减去8(4个2)，变为7
* 同样，对7进行上面的处理，新一轮计数为2（7包含2个2，不能包含4个2），因此总计数为6，将7减去4
* 对3进行上面的处理，这一轮计数为1，因此总计数变为7，将3减去2
* 对1进行上述处理，由于1小于2，所以停止
* 因此，15里面包含7个2，即商为7

由于每次将除数翻倍，所以会比方法一快很多
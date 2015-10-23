# Trick 2.2 - 枚舉子集合

有的時候我們在做子集合 DP 的時候，想要進行狀態轉移，這時候必須考慮當前集合的所有子集和。如果我們能夠利用「線性時間」（也就是 $$O(子集合數量)$$ 的時間）掃過所有子集和，那麼我們可以發現考慮所有狀態以及轉移所需要的 DP 時間從原本的 $$O(2^n\cdot 2^n)$$ 降到了 $$
\Theta\left(\sum_{k=0}^n {n\choose k} 2^k\right) = \Theta(3^n)
$$

超棒的吧！要怎麼做到呢？我們可以利用 [Trick 2.1](2.1/lowbit.md) 提及的 low-bit 不斷地找出目前枚舉到的最後一個元素，把它拿掉並且加回所有比它還小的元素：

```c++
for (subset = all; subset != 0; subset = (subset-1)&all) {
    // do something ...
}
```
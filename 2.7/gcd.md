# Trick 2.7 - 輾轉相除法

給定兩個不同時為零的整數 $$A, B$$，我們想要計算最大的正整數 $$d$$ 同時整除他們兩個。我們使用輾轉相除法實作可以得到以下方法：

```c++
int gcd(int A, int B) {
  if (B == 0) return A;
  return gcd(B, A%B);
}
```

為了避免遞迴呼叫造成不必要的時間浪費，我們可以使用非遞迴方法：

```c++
int gcd(int A, int B) {
  while (B != 0) {
    A %= B;
    swap(A, B);
  }
  return A;
}
```

然後利用 C++ 判斷會有 short circuit 特性，我們可以簡寫成兩行：

```c++
int gcd(int A, int B) {
  while (B && (A %= B) && (B %= A));
  return A+B;
}
```

## 現成的 __gcd 函數

要計算兩個數字的最大公因數，在 `<algorithm>` 裡面有提供現成的 `__gcd()` 函數，
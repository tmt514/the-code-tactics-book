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

然後利用 C++ 判斷式會有 [short circuit](https://en.wikipedia.org/wiki/Short-circuit_evaluation) 特性，我們可以簡寫成兩行：

```c++
int gcd(int A, int B) {
  while (B && (A %= B) && (B %= A));
  return A+B;
}
```

## 現成的 __gcd 函數

要計算兩個數字的最大公因數，在 `<algorithm>` 裡面有提供現成的 `__gcd()` 函數。很特別的是，如果這個方法是 generic (templated) 的。也就是說，如果我們想計算，例如兩個多項式的最大公因式，我們只要定義好多項式的取餘數、判斷是否等於零、（以及 copy by reference），就可以輕鬆算出！

### 參考資料

* http://stackoverflow.com/questions/24981380/implementation-of-the-in-built-gcd-method-in-c
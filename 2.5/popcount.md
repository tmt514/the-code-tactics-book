# Trick 2.5 - __builtin_popcount

要計算一個整數有多少個 1-bit，我們可以使用這個現成的函式。它的計算相當快喔，作法有點類似於在 interval tree 上面進行數位統計：先計算相鄰兩個 bit 的總和、再計算連續 4 個 bit 的總和、再計算連續 8 bits 的總和、然後是 16, 32, 64。

其他類似的 function 還有 `__builtin_parity()` （計算奇偶性）、`__builtin_ffs()`（最低 1-bit 是第幾位數）

## 參考資料

* https://gcc.gnu.org/onlinedocs/gcc/Other-Builtins.html
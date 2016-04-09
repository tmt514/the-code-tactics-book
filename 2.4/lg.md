# Trick 2.4 - __lg

當我們想快速知道一個整數最前面的 bit 是第幾個的時候，就可以用這個函數啦。由於它是透過 `__builtin_clz()` 這個函數計算的（counting leading zero），所以速度算是相當快。

## Notes

在 Mac 裡頭的 clang 編譯器似乎沒有 `__lg` 這個 function，直接存取 `__builtin_clz` 才能使用。

## 參考資料

* https://gcc.gnu.org/onlinedocs/libstdc++/libstdc++-api-4.5/a01023_source.html (第 992~1010 行)
# Trick 1.3 - c_str

這是一個可以把 C++ `std::string` 變成可唯讀的 `const char[]` 的好用東西。很多時候用 C++ string 方便處理的東西，最後要輸出的時候反而用 C 的 `puts`, `printf` 比較方便。這時候 `c_str()` 就派上用場啦。

## 對齊輸出

如果對 `<iomanip>` 裡頭 `fixed`, `setfill()`, `left`, `right`, `setw()` 不熟的朋友，可以使用 `printf` 輸出。

## 參考資料

* http://en.cppreference.com/w/cpp/io/manip/left
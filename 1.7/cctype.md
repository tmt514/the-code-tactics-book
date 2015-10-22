# Trick 1.7 - 大小寫轉換 tolower, toupper

在 `<cctype>` (C 語言的話請引入 `<ctype.h>` 標頭檔) 裡頭有著方便的函式，可以幫你把大小寫英文字母互相轉換。如果整個字串要換成大寫怎麼辦？這時候可以有兩種方式：利用迴圈、或是利用 Lambda 算子的概念套用在 `<algorithm>` 裡頭的 `std::transform` 上面。

```c++
for (auto &&x : str) {
    x = toupper(x);
}
```

```c++
transform(str.begin(), str.end(), str.begin(), toupper);
//        first iter,  last iter, result iter, operator
```
# Trick 1.6 - eof

在 C 語言中，EOF 的值是 `-1`。通常用 `getchar()` 或者是 `scanf()` 如果回傳的是 EOF 就代表讀到檔尾啦。如果我們用的是 `gets()` 那麼讀取失敗會得到 NULL。

那麼在 C++ 怎麼辦呢？`cin` 針對 eof 與讀取失敗有分開處理，也就是說，我們可以針對這個 `<istream>` 裡頭的 `cin`，呼叫 `cin.eof()` 或 `cin.fail()` 函式來得到現在的狀態。

所以「讀到檔尾結束」的 `<cstdio>` 版本是：

```c
int n;
while (scanf("%d", &n)!=EOF) {
    solve();
}
```

而 `<iostream>` 的版本則是：

```c++
int n;
while ((cin >> n) && !cin.eof()) {
    solve();
}
```

如果我們不關心 eof，只關心是否讀取失敗，那麼 `<iostream>`  的物件可以很貼心地幫我們轉換成 `bool`：

```c++
int n;
while (cin >> n) {      // (bool)(cin >> n) 讀完後等價於 !cin.fail()
    solve();
}
```

## 參考資料

* http://en.cppreference.com/w/cpp/io/basic_ios/operator_bool
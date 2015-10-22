# Trick 1.2 - stoi, atoi, stol, stoll

要怎麼把一個字串變成數字？常常會遇到輸入的資料是字串或數字混雜，這時候就得先把字串讀進來，然後再判斷它是字串還是數字。轉換的部分我們可以用 `stoi` 等現成的函數來處理。

```c++
string s;
cin >> s;
int n = std::stoi(s);    //C++11
```

還可以轉換成其他進位制喔，就不用自己寫轉換的函式了！

```c++
string s;
cin >> s;
int n = std::stoi(s, nullptr, 14);
```
# Trick 1.4 - stringstream 大絕招

想把數字印成字串嗎？`<cstring>` 裡頭有 `sprintf` 可以用，但是有的時候仍然不是那麼智慧（比方說，我要把字串分次接在一起的時候）這時候有個 `<ostream>` 來接收輸出不是很好嗎？

這時候就可以考慮 `stringstream` 了！超方便，把它當成一個可以動態讀出與寫入的字串就可以啦！

搭配 `getline()` 讀取一行未定長度之變數序列，相當好用噢！

## 實作 array join

假設我們今天有一個 vector (或 array)，我們想把它接成一個字串輸出，中間以逗號和空白格開，我們該怎麼做呢？我們可以利用 stringstream 作為輸出用的 buffer。

```c++
#include <sstream>
using namespace std;

string string_join(vector<int> arr, string delim = ", ") {  
    stringstream ret;
    for (int i = 0; i < arr.size(); i++) {
        ret << i;
        if (i+1 < arr.size()) {
            ret << delim;
        }
    }
    return ret.str();
}
```

但是我們可以用 `std::copy` 輕鬆做到以上的事情：

```c++
#include <iostream>
#include <sstream>
using namespace std;

string string_join(vector<int> arr, string delim = ", ") {
    stringstream ret;
    if (arr.size() == 0) return "";
    copy(arr.begin(), arr.end()-1, ostream_iterator<int>(ret, delim));
    ret << arr.back();
    return ret.str();
}
```
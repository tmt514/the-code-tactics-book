# Trick 1.1 - sync_with_stdio

`cin` 和 `cout` 不會比 `scanf` 或 `printf` 慢（太多）。如果你覺得有時間瓶頸的話，試一下在程式一開始的時候用

```c++
std::cin.sync_with_stdio(false);
std::cout.sync_with_stdio(false);
```

就可以了。引入 `#include <iostream>` 標頭檔（因為有 `cin` 跟 `cout`）。

## Tip

如果你發現還是 TLE 的話，可能是你的演算法太沒效率啦。這個方法只有在輸入/輸出量很大、你又堅持要用 cin 和 cout 的時候才會有顯著的效果。
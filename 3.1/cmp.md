# Trick 3.1 - 自定義比較函數排序

在使用 std::sort 排序的時候，我們可以傳入一個自定義的比較函數。比方說，我們想要把平面上的座標點，依據極角大小排序：

```cpp
struct Point {
    int x, y;
};

// 比較兩個點的極角角度值，這個是取代「小於」的定義。
bool cmp(const Point &A, const Point &B) const {
    return atan(A.y, A.x) < atan(B.y, B.x);
};
```

所以若我們有 `vector<Point> arr`，那麼我們可以這麼排序：

```cpp
std::sort(arr.begin(), arr.end(), cmp);
```

## 完整的用法

其實比較函數在編譯時，會被包裝成一個比較類別，並且重載其「括弧」的運算子。
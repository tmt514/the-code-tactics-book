# Trick 1.5 - 不要用 strtok

`strtok` 跟 `qsort` 一樣<s>超難用</s>，因為你永遠會搞混它的參數順序。

那要如何用替代方案呢？在 python 或 ruby 裡頭我們都可以用

```python
str.split()
```

以泛空白字元為分隔符號切開字串，在 PHP 裡頭用的是 `explode()`。在 C++ 似乎沒有這麼方便的東西，我們可以用 [Trick 1.4](1.4/sstream.md) 的 `stringstream` 來處理，也可以用 `<string>` 裡頭的 `find()` 找出分隔符號第一次出現的位置，再以 `substr()` 切開。

## 參考資料

* http://stackoverflow.com/questions/236129/split-a-string-in-c
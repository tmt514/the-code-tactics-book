# Trick 2.3 - 計數器

我們可以利用一個陣列來模擬計數器的顯示。當然，如果計數器是二進位的，我們也可以利用位移運算子直接進行計數的判斷。

為了實作方便，我們通常是用陣列的 counter[0] 這格作為最低 bit。

```c++
int counter[100] = {};
while (counter[n] == 0) { //當最高的位數是 0，表示還沒跑完所有數字
    // do something
    
    // 進行一個 +1 的這個動作
    int i = 0;
    for (i = 0; counter[i] == 9; counter[i++] = 0);
    counter[i]++;
}
```
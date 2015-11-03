# Trick 7.4 - 輸出效率

cout, printf, stringstream 相較之下，cout 會比後兩者慢一些。但是如果用更底層的輸出，可以考慮使用 puts, fwrite, cout.write 等

據說最花時間的是 `std::endl`

## 參考資料

* http://stackoverflow.com/questions/1924530/mixing-cout-and-printf-for-faster-output
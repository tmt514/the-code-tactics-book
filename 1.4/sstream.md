# Trick 1.4 - stringstream 大絕招

想把數字印成字串嗎？`<cstring>` 裡頭有 `sprintf` 可以用，但是有的時候仍然不是那麼智慧（比方說，我要把字串分次接在一起的時候）這時候有個 `<ostream>` 來接收輸出不是很好嗎？
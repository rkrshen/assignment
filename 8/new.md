同源政策===>（不同網域 ）

安全性的考量


CORS
access-control-allow-origin: *

JSONP

利用 src 不受同源限制的特性，直接載入一隻帶參數的js，當作是發 request，用一個 function 包裝起來
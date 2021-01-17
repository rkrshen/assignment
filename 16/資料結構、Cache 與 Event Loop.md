cache


資料結構

堆疊
stack

佇列
queue


!!call stack 



callback queue


順序
call stack -->  callback queue



Expires跟Cache-Control: max-age決定這份快取的「新鮮度」，也就是什麼時候「過期」。在過期之前，瀏覽器「不會」發送出任何 Request
當快取過期之後，可以用If-Modified-Since或是If-None-Match詢問 Server 有沒有新的資源，如果有的話就回傳新的，沒有的話就回傳 Status code 304，代表快取裡面的資源還能繼續沿用。





之所以快取的機制會有點小複雜，是因為分成不同的部分，每一個相關的 Header 其實都是在負責不同的部分。例如說Expires跟max-age是在負責看這個快取是不是「新鮮」，Last-Modified, If-Modified-Since, Etag, If-None-Match是負責詢問這個快取能不能「繼續使用」，而no-cache與no-store則是代表到底要不要使用快取，以及應該如何使用。


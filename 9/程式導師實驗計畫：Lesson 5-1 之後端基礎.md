
php
變數都要用＄
字串都要''
連接用 . 
var_dump()印出陣列
print_r()也可以



在終端機想看看php 執行的結果
指令 php 檔案名稱

network===>
清除快取！！！
Disable cache勾起來！勾起來！

跳轉的紀錄也要看
Preserve log勾起來！勾起來！

如果有錯誤，停止執行以下程  式
die()

sql指令裡面塞變數
通常要用 insert into user(username) values('" $username"')
用sprintf()
可以變成
sprintf("insert into user(username) values('%s)",$username）


看看影響的列數
避免空刪除或者空編輯
$conn->affected_rows >= 1
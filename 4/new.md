GET
GET 方法請求展示指定資源。使用 GET 的請求只應用於取得資料。
HEAD
HEAD 方法請求與 GET 方法相同的回應，但它沒有回應主體（response body）。
POST
POST 方法用於提交指定資源的實體，通常會改變伺服器的狀態或副作用（side effect）。
PUT
PUT 方法會取代指定資源所酬載請求（request payload）的所有表現。
DELETE
DELETE 方法會刪除指定資源.
CONNECT
CONNECT 方法會和指定資源標明的伺服器之間，建立隧道（tunnel）。
OPTIONS
OPTIONS 方法描述指定資源的溝通方法（communication option）。
TRACE
TRACE 方法會與指定資源標明的伺服器之間，執行迴路返回測試（loop-back test）。
PATCH
PATCH 方法套用指定資源的部份修改。



資訊回應 (Informational responses, 100–199),
成功回應 (Successful responses, 200–299),
重定向 (Redirects, 300–399),
用戶端錯誤 (Client errors, 400–499),
伺服器端錯誤 (Server errors, 500–599).


200=>
請求成功。成功的意義依照 HTTP 方法而定：
GET：資源成功獲取並於訊息主體中發送。
HEAD：entity 標頭已於訊息主體中。
POST：已傳送訊息主體中的 resource describing the result of the action。
TRACE：伺服器已接收到訊息主體內含的請求訊息。



TCP/IP 是電腦網路通訊協定，分為四個層級:
應用層 (HTTP、FTP ...)
傳送層 (TCP、UDP ...)
網路層 (IP、ICMP ...)
鏈結層 (ARP、NDP ...)



固定 IP: IP 位址是固定的
浮動 IP: IP 位址會隨著每次連線而改變，不易受駭客攻擊
虛擬 IP: 在內網才能互相連接，對外為同一固定或浮動的 IP，通常為 192.168 開頭


TCP:
三次握手=>確保資料送達 可靠廣用
UDP＝>快速常發生的傳輸方式 用在視訊 即時通知
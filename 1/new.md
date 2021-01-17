
pwd
印出所在位置
ls
印出現在資料夾底下的檔案
ls -at 
可以列印出檔案的詳細資料。
cd
切換資料夾
cd .. 
可以切換到目前資料夾的上一層
man
使用說明手冊
 man ls 
 搜尋 ls 的功用
touch
建立檔案或是更新檔案時間
touch 
一個資料夾沒有的檔案名稱，就會建立一個為此名稱的檔案
touch 過的檔案只會更新檔案時間，不會更動任何檔案內容
rm
刪除檔案或資料夾

rm -r aaa
檔案名稱(或資料夾名稱)刪除。
mkdir
建立資料夾
mkdir aaa
mv
移動檔案或是改名
mv 
檔案名稱 當前路徑下有的資料夾名稱
cp
複製檔案
cp aaa
新的檔案名稱
cp -r aaa 新的資料夾名稱

vim
文字編輯器
 +i
 可以插入文字與編輯檔案
 :q
 離開編輯器
 :wq 
 儲存檔案後離開。
grep
抓取關鍵字
抓取檔案的關鍵字 ：grep 欲抓取的關鍵字並且把有關鍵字的那一行列出來。
cat
連接檔案或是印出單一檔案內容

less
也是印出單一檔案內容
但是可以藉著上下滑動查看，要離開頁面的話按 q
curl
送出 request
redirection（ 重新導向）
 


 ![](https://i.imgur.com/HOdaN3S.png)
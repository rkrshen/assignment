

cil 指令


1. command line for window 

官網上連結有附贈git bash
(跑指令用)

cmder 跟 git bash 選一個裝就好

pwd目前位置
ls目前資料夾底下所有檔案
安裝完測試一下


2. mac
iterm2
漂亮的終端機可以開分頁






> 第二步<指令


| Mac      | Windows  | 說明         |
| -------- | -------- | --------    |
| cd       | cd       | 進入資料夾    |
| -------- | -------- | --------    |
| pwd       | pwd     | 目前所在位置  |
| -------- | -------- | --------    |
| ls       | dir      | 查詢資料夾內容 |
| -------- | -------- | --------    |
| pwd      | cd       | 列出資料夾位址 |
| -------- | -------- | --------    |
| whoami   | whoami   | 查詢使用者是誰 |
| -------- | -------- | --------    |
| touch    | *        | 建立檔案     |
| -------- | -------- | --------    |
| rm       | del      | 刪除檔案     |
| -------- | -------- | --------    |
| clear    | cls      | 清除終端機畫面 |
| -------- | -------- | --------    |
| mkdir    | mkdir    | 建立目錄     |

ls -al 詳細資料並且用list列表
-後面可以加參數

cd ..回上一層
cd ~ user/使用者

cd 按tab可自動完成

man  使用說手冊 
q 離開使用說手冊

touch <檔案名稱> 更改最後修改時間
如果檔案不存在就建立一個如此名的檔案

rm 刪除檔案 (不能刪除資料夾)
可用rmdir或者 rm -r <資料夾名稱>


mv 移動檔案或改名

mv 檔案 <資料夾> 

mv 檔案 ..  移到上一層

改名
mv 檔案名稱 新名稱


複製檔案

cp 檔案名稱 新名稱
資料夾沒辦法複製


複製資料夾
cp -r 資料夾名稱 新資料夾名稱



vim

文字編輯器
mac有
可打
vi 或者ｖ


vi 檔案名稱

按i進入編輯模式
esc進入普通模式(可刪除複製貼上但不可編輯)

:q出來並選擇要不要儲存
:wq寫完並且出去



cat用來連結檔案用
但如果沒有其他檔案或開啟檔案內容


grep抓取關鍵字

grep y 檔案名稱 在搜尋檔案中的關鍵字y

wget下載檔案(不是內建的)
圖片和網頁原始碼

open 可以打開圖片

* curl 送出request

擷取header
curl -I


redirection重新導向

ls -al > <aaa>

箭頭是輸出並儲存成aaa的檔案

echo 印出

>會把檔案內容整個蓋掉
>>才可以新增



pipe |

可以把左邊指令的輸出變成右邊指令的輸入
cat aaa | grep p
===
grep p aaa


cat aaa | grep p > result

把aaa檔案中有p得內容存成result



github pages 
可以把上面可以把上面變成一個靜態網頁
setting => github pages => 設定好source => save
他會給你一個網址
會有一個網址可以呈現




＊ commit message打錯了
更改commit message
git commit --amend
改好 :wq
要在當下改


＊ 我 commit 了可是我又不想 commit 了

git reset HEAD^
回到上一個commit
HEAD^=>上一個commit


git reset HEAD^ --hard
我上一個commit都不要了


git reset HEAD^ --soft =>預設是這個
我回到上一個commit 修正
上一個commit 我不要
但內容我還是要
因此我回去修改
並且commit


＊ 還沒 commit，但我改的東西我不想要了

git checkout -- <aaa>


＊ 我想改 branch 的名字
git branch -m <aaa>


＊ 想摘下遠端的 branch 給你
git branch -v 檢查
用 git checkout branch的名稱
就可以抓下來



HOOK
發生某事的時候通知我
做一些判斷
應該用不到















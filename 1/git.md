

window

git-scm.com
下載安裝完打開git-bash


在 Mac 底下的話請你打開 Terminal（右上角搜尋的按鈕按下去，輸入 terminal 就找得到了），並且輸入 git --version，按下 enter。

如果你的 MacOS 版本是 10.9 以上，就會自動跳出視窗指引你去安裝，或是你也可以參考 Git 官網的教學，直接下載安裝檔。


git init 初始化
要對這個資料夾開始做版本控制
裡面會有一個檔案叫.git

git status
確認他的狀態


git add
決定是否要加入版本控制
untracked   沒有
staged  有


git rm --cashed 檔案名稱
把這個檔案放入untracked（不被版本控制）

git add .
全部加入版本控制



git commit

 要輸入敘述
 git commit -m "敘述"



git log 歷史紀錄


git log --oneline  簡短地史紀錄

git checkout 回到某個版本

.gitignore 忽略檔案

git commit -am '敘述'
可以合併git add . 和 git commit -m "敘述"
但不會加入新建立的檔案


創立版本控制的步驟
git init
.gitignore
git add . 
git commit -am '敘述'


git diff
可以看到更改的內容
按q可以出來  

git branch <aaa> 開一個新的分支叫做aaa

git branch -v 看到目前版本

git branch -d 刪除分支



git merge <aaa>
master 把 <aaa> 併進來



新增遠端倉庫步驟
點選＋＋點選＋＋
取名字
敘述
以上為建立好一個遠端倉庫
然後 git remote add origin '網址'
建立指向遠端倉庫的窗口
git push -u origin master
把本地推上去


git pull origin master
拉下來


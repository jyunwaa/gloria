## 管理方式

所有賬號的Cookie保存在`Glory/identities`文件夾中，每個賬號以`賬號名稱.txt`命名，以文本文檔的形式存在，文件內容是賬號的Cookie。

每新增或者刪除一個賬號只需新建一個文件或者刪除對應的文件即可。

`identities`文件夾的目錄結構：

```
Glory
├─identities
│  ├─帳號一.txt
│  ├─帳號二.txt
│  ├─...
├─...
```

## Cookie

簡單來說，可以把cookie看作是每個賬號登陸後獲得的唯一的身份信息，每次向新浪發出請求時，都會附帶上cookie，新浪的服務器因此也能識別出具體的用戶。

## 獲取 Cookie

### 登錄新浪

瀏覽器輸入：

```
https://weibo.cn/
```

如圖：

![](https://p.pstatp.com/origin/1380200010bcce54abaa4)

點擊登錄，輸入賬號密碼，登陸新浪微博。

有可能會跳轉到如圖頁面：

![](https://api.superbed.cn/static/images/2020/08/27/5f479abc160a154a67635ac2.jpg)

如果跳轉到該頁面，則再次手動輸入剛才的地址，如圖：

![](https://p.pstatp.com/origin/febf0002785510a6cd7a)

若登陸成功，則該頁面會顯示自己的信息，如上圖：賬號名為`GEM迷183003`。

### 複製 Cookie

此時按下`F12`，進入開發者選項，點擊`Network`，如圖：

![](https://p.pstatp.com/origin/fea20002cdab7b52d93f)

按`F5`刷新網頁，如圖：

![](https://p.pstatp.com/origin/13778000165ad193a8192)

如上圖，點擊`weibo.cn`，再點擊`Headers`，找到`cookie`，然後複製劃藍線的部分（已打碼）。

## 添加賬號

打開`Glory/identities`文件夾，新建文件`GEM迷183003.txt`（這裡的文件名根據自身實際情況更改，不一定必須和微博名相同，注意後綴`.txt`必須有），如圖：

![](https://p.pstatp.com/origin/1379f0000dbeb4d9e4188)

打開`GEM迷183003.txt` 將剛才複製的 cookie 粘貼進去，`Ctrl` + `S` 保存，如圖：

![](https://p.pstatp.com/origin/ffe40002668fe870f5ed)

## 退出賬號

因為我們往往不止有一個賬號，所以需要獲取多個賬號的 cookie，但是前一個賬號登陸後需要退出，此時不能點擊首頁的`退出`鏈接，這個鏈接會使 cookie 立馬失效，我們需要通過手動清除瀏覽器的 cookie 的方式進行退出。

保持剛才的開發者選項，點擊`Application`，找到`Storage`下的`Cookies`，右擊`https://weibo.cn`，點擊`Clear`，如圖：

![](https://p.pstatp.com/origin/1389a0000055cb2d0498d)

按`F12`退出開發者選項，再按`F5`刷新網頁，登陸狀態已經消失，如圖：

![](https://p.pstatp.com/origin/ffe30002cad77a7144b9)

> Cookie 的有效期一般在一個月以上。

## 查看所有賬號

進入`Glory`文件夾，地址欄輸入`cmd`，如圖：

![](https://p.pstatp.com/origin/1383300009a39d90a81a4)

按下回車，在彈出的命令行窗口中輸入：

```cmd
glory account:view
```

按下回車，如圖：

![](https://p.pstatp.com/origin/1372100018c17f8306aad)

注意每個帳號的`AccountID`，它在執行命令時用於指定賬號，此外，在`Glory/identities`文件夾內部發生變化時它可能會變化。



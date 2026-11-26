# 迪諾文字大尋寶（繁體中文＋日文）

四個雙語 APP 之一：**繁中日**。

國小生字學習遊戲，繁體中文與日文可在畫面右上角切換。純網頁程式，不需要伺服器程式或資料庫。
四個 APP 各自獨立、各有自己的儲存庫，其他三個：[繁中英](https://github.com/claudecat30-sys/dino-word-hunt-tw)、[簡中英](https://github.com/claudecat30-sys/dino-word-hunt-cn)、[簡中日](https://github.com/claudecat30-sys/dino-word-hunt-cnja)。

線上版：https://claudecat30-sys.github.io/dino-word-hunt-twja/

## 執行

- 入口是 `index.html`。放到任何靜態網頁空間就能用，路徑都是相對路徑。
- 也可以直接包進 App 的 WebView，載入 `index.html`。
- 語音辨識（唸讀遊戲的麥克風）需要 https。

## 內容

| 檔案 | 說明 |
|---|---|
| `index.html` | 全部的程式與課程資料 |
| `img.js` | 圖片（內嵌在程式裡） |
| `accounts.js` | 登入帳號清單與測試用的自動填入開關 |
| `audio/index.js` | 預錄語音索引 |
| `audio/zh/`、`audio/en/` | 預錄語音 mp3（`en` 資料夾放第二語言：日文） |

共 68,754 個檔案、約 985 MB，其中絕大部分是語音檔。

## 登入

- 登入只在裝置上比對 `accounts.js` 裡的帳號，沒有伺服器驗證，不能當成真正的權限管控。
- 目前是測試設定：`window.DINO_LOGIN_PREFILL=true` 會在登入畫面自動填好第一組帳號密碼。正式上線請改成 `false`，並換掉測試帳號。
- 勾選「記住帳號密碼」會存在裝置上 180 天。

## 關閉遊戲

右上角的關閉按鈕在網頁裡會停在道別畫面。包成 App 時，外殼可以提供 `window.DinoApp.exit()` 讓它真的結束程式。

## 注意

這個資料夾是建置產物，請不要直接修改；要改內容請改原始專案後重新建置。

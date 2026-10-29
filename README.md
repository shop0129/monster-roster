# 小怪獸放電所｜排班系統靜態網站版

## 現況
Supabase 雲端專案已建立，資料庫與員工管理函式已部署。前端網頁需要透過 GitHub Pages 等靜態網頁服務發布。

## GitHub Pages 發布方式
1. 在 GitHub 登入，建立 **Public** Repository，例如 `monster-roster`。（注意：Public 網站原始碼任何人可見，切勿放私密 API 金鑰）
2. 將 `index.html`、`config.js`、`manifest.webmanifest` 上傳到 repository 根目錄。不要上傳後端私密金鑰。
3. 進入 Settings → Pages → Build and deployment → Deploy from a branch，選 main / (root)，按 Save。
4. 等 GitHub 顯示網站網址，開啟後輸入 `shop0129@gmail.com` 與自己設定的密碼，點「首次註冊店長」。
5. 到 Gmail 開啟 Supabase 寄來的確認信，確認後回到登入畫面。
6. 若驗證信跳轉至錯誤網站，需在 Supabase Authentication → URL Configuration，將 GitHub Pages 網址設為 Site URL，並加入 Redirect URLs。

## 安全
`config.js` 僅包含 Supabase 公開 publishable key（適合前端公開），不包含 service_role。資料表已設定 RLS，員工只能讀取自己的班次；店長才可修改班次。

## 注意
目前尚未完成真實帳號登入及員工流程端到端驗收。請先用一位測試員工，確認排班新增、登入只見自己班次、停用帳號流程，再正式使用。

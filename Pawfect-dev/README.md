# Pawfect 專題開發規範

## GIT版控規範
  - 開發前記得fetch最新版本，確認無誤合併後進行開發
  - 在dev分支上開"feature/自訂名稱"分支開發
  - 開發完畢push後，透過 GitHub申請一個 dev 合併 "feature/自訂名稱" 進度的PR
  - 全員確認沒問題後，Chung 審核 PR 通過 merge 進dev
  - 最終確認dev版本沒問題再合併到 main 分支，並進行後續deploy部屬到gh-page
  - 如遇衝突不知如何解決，可先在discord討論

## 程式碼規範
  - 開發時確認關閉自動排版功能，避免影響其他人的code
  - 共同頁面，請在各自區塊內更新自己的code
  - 命名時開頭先以頁面再以各自區塊開頭命名，例如index的banner區塊命名時以"index-banner-名稱"作命名
  - 可以的話，將自己區塊的class包在最外層的class內
  - 自己寫顏色樣式的時候，請使用寫好的變數，例如$primary
  - 不確定時皆可先discord討論~~



## Node.js 版本
  - 專案的 Node.js 版本需為 v16 以上
  - 查看自己版本指令：`node -v`


## 指令列表
- `npm install` - 初次下載該範例專案後，需要使用 npm install 來安裝套件
- `npm run dev` - 執行開發模式
  - 若沒有自動開啟瀏覽器，可嘗試手動在瀏覽器上輸入
    `http://localhost:5173/<專案名稱>/pages/index.html`
- `npm run build` - 執行編譯模式（不會開啟瀏覽器）
- `npm ru deploy` - 自動化部署

## 資料夾結構
  - assets # 靜態資源放置處
    - images # 圖片放置處
    - scss # SCSS 的樣式放置處

  - layout # ejs 模板放置處
  - pages # 頁面放置處

- JavaScript 程式碼可寫在 main.js 檔案

### 注意事項
- 已將 pages 資料夾內的 index.html 預設為首頁，建議不要任意修改 index.html 的檔案名稱
- .gitignore 檔案是用來忽略掉不該上傳到 GitHub 的檔案（例如 node_modules），請不要移除 .gitignore

## 開發模式的監聽
vite 專案執行開發模式 `npm run dev` 後即會自動監聽，不需要使用 `Live Sass Compiler` 的 `Watch SCSS` 功能


## 部署 gh-pages 流程說明
### Windows 版本
1. 在 GitHub 建立一個新的 Repository

2. 部署前請務必先將原始碼上傳到 GitHub Repository 也就是初始化 GitHub，因此通常第一步驟會在專案終端機輸入以下指令
```cmd
git init # 若已經初始化過就可以不用輸入
git add .
git commit -m 'first commit'
git branch -M main
git remote add origin [GitHub Repositories Url]
git push -u origin main // 僅限第一次輸入，往後只需要輸入 git push
```

3. 初始化完畢後，執行 `npm run deploy` 指令進行自動化部署

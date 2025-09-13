# 網頁切版直播班 Vite 範例

## Node.js 版本

- 專案的 Node.js 版本需為 v18 以上
- 查看自己版本指令：`node -v`

## 指令列表

- `npm install` - 初次下載該範例專案後，需要使用 npm install 來安裝套件
- `npm run dev` - 執行開發模式
  - 若沒有自動開啟瀏覽器，可嘗試手動在瀏覽器上輸入
    `http://localhost:5173/<專案名稱>/pages/index.html`
- `npm run build` - 執行編譯模式（不會開啟瀏覽器）
- `npm run deploy` - 自動化部署

## 資料夾結構

├── .gitignore # Git 忽略文件，用來指定不需上傳至 GitHub 的檔案或目錄
├── README.md # 項目說明文件，包含專案說明、指令列表及部署流程等資訊
├── vite.config.js # Vite 配置檔案，設定 base 路徑、插件（如 EJS、live-reload）、伺服器選項及 build 設定
├── package.json # 項目設定文件，定義專案名稱、版本、腳本（如 dev、build、deploy 等指令）
├── package-lock.json # NPM 依賴鎖定文件，確保依賴版本一致，包含所有套件的詳細版本資訊
├── main.js # 主 JavaScript 檔案，用來匯入樣式（如 SCSS）或執行 JavaScript 程式碼
├── assets/ # 靜態資源資料夾，用來放置圖片、圖標及 SCSS 樣式
│ ├── icon/ # 網頁圖標
│ ├── image/ # 網頁圖片
│ │ ├── Logo/ # 網站 Logo
│ └── scss/ # SCSS 樣式主資料夾
│ ├── layout/ # SCSS 樣式子資料夾，用來存放 layout 相關樣式
│ │ ├── footer.scss # SCSS 檔案，用來定義頁面底部樣式（頁尾樣式寫這裡）
│ │ └── header.scss # SCSS 檔案，用來定義頁面頂部樣式（頁首樣式寫這裡）
│ ├── pages/ # SCSS 樣式子資料夾，用來存放 pages 相關樣式
│ │ └── index.scss # SCSS 檔案，用來定義首頁樣式
│ ├── all.css # 編譯後的 CSS 檔案
│ └── all.css.map # CSS 映射檔案
├── layout/ # EJS 模板資料夾，用來放置 EJS 模板檔案
│ ├── footer.ejs # EJS 模板檔案，用來定義頁面底部內容（頁尾結構寫這裡）
│ └── header.ejs # EJS 模板檔案，用來定義頁面頂部內容（頁首結構寫這裡）
└── pages/ # 頁面資料夾，用來放置 HTML 或 EJS 頁面檔案
├── index.html # 首頁 HTML 檔案，作為預設開啟頁面
├── MemberCenter.html # 會員中心頁面 HTML 檔案
└── ProductList.html # 產品列表頁面 HTML 檔案

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

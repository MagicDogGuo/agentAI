# GitHub Pages 部署說明

此 Unity WebGL 專案已設定為使用**未壓縮**資源，以相容 GitHub Pages（無法設定 `Content-Encoding`）。

## Unity 建構設定

1. **Edit → Project Settings → Player**
2. 選擇 **WebGL** 平台
3. 展開 **Publishing Settings**
4. 將 **Compression Format** 設為 **Disabled**
5. 執行 **File → Build Settings → Build** 輸出 WebGL

## 部署時必須包含的檔案

建構完成後，請將整個輸出資料夾的內容部署到 GitHub 倉庫，並確保 **Build** 目錄內包含：

- `Web.loader.js`
- `Web.framework.js`
- `Web.data`
- `Web.wasm`

若缺少 `Web.framework.js`、`Web.data`、`Web.wasm`，請確認已將 Compression Format 設為 Disabled 後重新建構。

## GitHub Pages 設定

在倉庫 **Settings → Pages** 中，將 Source 設為部署分支（例如 `main`）的根目錄或 `/docs`（依你放置檔案的目錄而定）。

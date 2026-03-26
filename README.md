# 動物保護資訊查詢系統

提供彰化縣、嘉義市、桃園市、南投縣的動物保護相關資訊查詢，含後台管理功能。

---

## 檔案結構

```
site/
├── index.html   ─ 主查詢頁面
├── admin.html   ─ 後台管理頁面
├── style.css    ─ 共用樣式
├── data.json    ─ 資料來源（需自行放置）
└── README.md    ─ 本說明文件
```

---

## GitHub Pages 部署步驟

### 1. 建立 GitHub Repository

1. 前往 [https://github.com](https://github.com) 並登入帳號
2. 點擊右上角「＋」→「New repository」
3. 填寫 Repository name（例如：`animal-protection-info`）
4. 設定為 **Public**
5. 點擊「Create repository」

### 2. 上傳網站檔案

**方法 A：網頁介面（初學者適用）**

1. 進入剛建立的 repository
2. 點擊「Add file」→「Upload files」
3. 將 `site/` 資料夾內所有檔案拖曳上傳：
   - `index.html`
   - `admin.html`
   - `style.css`
   - `data.json`
4. 填寫 Commit message（例如：`初始上傳`）
5. 點擊「Commit changes」

**方法 B：Git 指令**

```bash
cd /path/to/site
git init
git add .
git commit -m "初始上傳"
git remote add origin https://github.com/你的帳號/animal-protection-info.git
git push -u origin main
```

### 3. 啟用 GitHub Pages

1. 進入 repository 頁面
2. 點擊上方「Settings」
3. 左側選單找「Pages」
4. 在「Branch」選擇 **main**，資料夾選 **/ (root)**
5. 點擊「Save」
6. 等待約 1–2 分鐘後，頁面會顯示網址

### 4. 取得網址

啟用後網址格式為：

```
https://你的帳號.github.io/animal-protection-info/
```

---

## 後台使用說明

1. 點擊首頁右上角「⚙ 管理」按鈕
2. 輸入密碼：**1959**
3. 從左側樹狀結構選擇縣市或主題進行編輯
4. 可編輯項目：問題、答案、電話、連結、圖片
5. 可設定各縣市跑馬燈文字
6. 完成後點擊「**💾 儲存所有變更**」

---

## 資料管理

### 匯出資料

點擊「📥 匯出 JSON」即可下載完整的 `data.json`，包含所有後台編輯的內容。

### 匯入資料

點擊「📤 匯入 JSON」選擇 JSON 檔案，可覆蓋現有資料。

---

## 注意事項

### localStorage 限制

- 後台編輯的資料儲存在瀏覽器的 localStorage 中
- **不同瀏覽器、不同裝置無法共享資料**
- 清除瀏覽器快取會導致資料遺失
- **強烈建議定期使用「匯出 JSON」功能備份資料**
- 若要讓所有使用者看到最新資料，需將匯出的 `data.json` 上傳至 GitHub 覆蓋原始檔案

### 圖片上傳

- 圖片以 Base64 格式儲存，會增加 localStorage 佔用空間
- 建議上傳的圖片大小不超過 500KB
- localStorage 上限約 5–10MB（視瀏覽器而定）

### 搜尋功能

- 關鍵字搜尋為即時搜尋，可跨縣市找到相關資料
- 搜尋結果會標示所屬縣市與主題

---

## 技術規格

- 純靜態網站（HTML / CSS / JavaScript）
- 無需後端伺服器
- 不依賴任何第三方框架
- ES6+ 語法，支援現代瀏覽器
- 響應式設計，支援手機瀏覽

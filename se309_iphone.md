# SE-309 儀表板：iPhone / iOS 使用指南

由於 Apple iOS 系統的限制，一般的 Safari、Chrome 或 Edge 瀏覽器**不支援 Web Bluetooth API**（即 `navigator.bluetooth`）。

要在 iPhone 上正常連接 SE-309 藍牙溫度計，請按照以下步驟操作：

---

## 步驟一：下載支援藍牙網頁的專用瀏覽器

請至 App Store 免費下載以下任一支援 Web Bluetooth 的瀏覽器 App：

1. **Bluefy – Web BLE Browser**（推薦，免費且支援度高）
2. **WebBLE Browser**

---

## 步驟二：將網頁部署至 HTTPS 伺服器

Web Bluetooth API 出於安全性考量，**強制要求網站必須使用 `https://` 加密連線**（或者 `localhost`）。您無法直接在 iPhone 上雙擊開啟單機 `.html` 檔案。

### 建議的免費託管方式（幾分鐘內完成）：

1. **GitHub Pages**：
   - 將 `index.html` 上傳至 GitHub 儲存庫（Repository）。
   - 在 Settings -> Pages 中開啟 GitHub Pages 功能。
   - 即可獲得一個免費的 `https://yourname.github.io/repository` 網址。
2. **Vercel / Netlify**：
   - 直接把 `index.html` 拖放上傳，幾秒鐘即可獲得免費 HTTPS 網址。

---

## 步驟三：在 iPhone 上進行連接

1. 打開 iPhone 的 **設定** -> **藍牙**，確認藍牙已開啟。
2. 開啟剛剛下載的 **Bluefy** 瀏覽器。
3. 在 Bluefy 的網址列輸入您的 **HTTPS 網址**。
4. 點擊網頁上的 **「Connect SE-309」** 按鈕。
5. 首次使用時，Bluefy 會跳出授權提示，請允許 **藍牙存取權限**。
6. 在裝置搜尋清單中選擇您的 **SE-309** 裝置即可開始實時監視！

---

## 常見問題與排障 (Troubleshooting)

| 問題現象 | 原因與解法 |
| :--- | :--- |
| **點擊連接按鈕沒有反應** | 請確認您不是使用原生 Safari。請改用 **Bluefy** 瀏覽器。 |
| **提示 `navigator.bluetooth is undefined`** | 網址未包含 `https://`，請確認網站已使用 SSL 加密安全連線。 |
| **搜尋不到 SE-309 裝置** | 1. 確認 SE-309 儀表已開機並開啟藍牙廣播。<br>2. 確認該裝置未被其他手機或電腦的藍牙連線佔用。 |
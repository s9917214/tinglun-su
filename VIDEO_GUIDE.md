# 影片嵌入完整指南

這個作品集支援三種影片來源：YouTube、Google Drive 和本地影片。以下是詳細的使用方法。

---

## 📺 方案 1: YouTube 影片（推薦）

### 優點
- ✅ 免費、無容量限制
- ✅ 載入速度快、全球 CDN
- ✅ 自動調整畫質
- ✅ SEO 友善
- ✅ 可設定為「不公開」(只有有連結的人可看)

### 步驟

#### 1. 上傳影片到 YouTube

1. 登入 YouTube
2. 點擊右上角「建立」→「上傳影片」
3. 選擇影片檔案
4. 設定隱私權：
   - **公開** - 任何人都能搜尋
   - **不公開** - 只有有連結的人可看 ✅ 推薦
   - **私人** - 只有你看得到（不適合網站）

#### 2. 取得影片 ID

上傳完成後，YouTube 影片網址格式：
```
https://www.youtube.com/watch?v=dQw4w9WgXcQ
                                 ^^^^^^^^^^^
                                 這就是影片 ID
```

#### 3. 更新 HTML 程式碼

在 `index.html` 中找到這段：

```html
<!-- YouTube 影片示範 -->
<div class="video-wrapper" data-video-type="youtube">
    <iframe
        src="https://www.youtube.com/embed/dQw4w9WgXcQ"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen>
    </iframe>
</div>
```

**替換 `dQw4w9WgXcQ` 為你的影片 ID**

---

## 💾 方案 2: Google Drive 影片

### 優點
- ✅ 免費 15GB 儲存空間
- ✅ 隱私控制好
- ✅ 可設定密碼保護
- ✅ 不需要額外平台帳號

### 缺點
- ⚠️ 載入速度較 YouTube 慢
- ⚠️ 可能被 Google 限流（太多人觀看時）

### 步驟

#### 1. 上傳影片到 Google Drive

1. 前往 https://drive.google.com
2. 點擊左上角「新增」→「檔案上傳」
3. 選擇你的影片檔案
4. 等待上傳完成

#### 2. 設定分享權限

1. 右鍵點擊影片檔案 → 「分享」
2. 點擊「變更」
3. 選擇「知道連結的任何人」
4. 權限設為「檢視者」
5. 點擊「複製連結」

#### 3. 取得檔案 ID

Google Drive 連結格式：
```
https://drive.google.com/file/d/1EXAMPLE_FILE_ID_HERE/view?usp=sharing
                                 ^^^^^^^^^^^^^^^^^^^^
                                 這就是檔案 ID
```

#### 4. 更新 HTML 程式碼

在 `index.html` 中找到這段：

```html
<!-- Google Drive 影片示範 -->
<div class="video-wrapper" data-video-type="gdrive">
    <iframe
        src="https://drive.google.com/file/d/1EXAMPLE_FILE_ID/preview"
        allow="autoplay">
    </iframe>
</div>
```

**替換 `1EXAMPLE_FILE_ID` 為你的檔案 ID**

**重要**：URL 格式必須是：
```
https://drive.google.com/file/d/你的檔案ID/preview
                                            ^^^^^^
                                            一定要是 preview 不是 view
```

---

## 📁 方案 3: 本地影片

### 優點
- ✅ 完全控制
- ✅ 無外部依賴
- ✅ 載入快（使用者電腦或伺服器）

### 缺點
- ⚠️ GitHub Pages 有 1GB 總容量限制
- ⚠️ 需要手動處理影片格式
- ⚠️ 佔用倉庫空間

### 適合情境
- 影片檔案小於 50MB
- 需要完全離線訪問
- 不想依賴第三方平台

### 步驟

#### 1. 準備影片檔案

**建議規格：**
- 格式：MP4 (H.264) + WebM (VP9) 雙格式
- 解析度：1920x1080 或 1280x720
- 位元率：2-5 Mbps
- 檔案大小：盡量 < 50MB

**壓縮影片工具：**
- **HandBrake** (免費) - https://handbrake.fr/
- **FFmpeg** (命令列)：
  ```bash
  # 壓縮為 MP4
  ffmpeg -i input.mov -vcodec h264 -acodec aac -b:v 2M output.mp4

  # 轉換為 WebM (可選，提供更好的瀏覽器兼容性)
  ffmpeg -i input.mov -c:v libvpx-vp9 -b:v 2M output.webm
  ```

#### 2. 建立 videos 資料夾

在 `academic-portfolio` 資料夾中建立 `videos` 資料夾：

```
academic-portfolio/
├── index.html
├── style.css
├── script.js
└── videos/              ← 新建這個資料夾
    ├── project1.mp4
    ├── project1.webm    (可選)
    └── poster.jpg       (影片預覽圖)
```

#### 3. 建立影片縮圖（poster）

影片縮圖是影片載入前顯示的圖片：

**方法 A：使用 FFmpeg 擷取**
```bash
ffmpeg -i videos/project1.mp4 -ss 00:00:05 -frames:v 1 videos/project1-poster.jpg
```

**方法 B：手動截圖**
- 播放影片
- 在想要的畫面暫停
- 截圖並儲存為 JPG

#### 4. 更新 HTML 程式碼

在 `index.html` 中找到這段：

```html
<!-- 本地影片示範 -->
<div class="video-wrapper" data-video-type="local">
    <video controls preload="metadata" poster="videos/project1-poster.jpg">
        <source src="videos/project1.mp4" type="video/mp4">
        <source src="videos/project1.webm" type="video/webm">
        您的瀏覽器不支援影片播放。
    </video>
</div>
```

**替換檔案路徑：**
- `videos/project1-poster.jpg` → 你的縮圖路徑
- `videos/project1.mp4` → 你的 MP4 影片路徑
- `videos/project1.webm` → 你的 WebM 影片路徑（可選）

---

## 🔄 如何選擇最適合的方案

### 推薦決策樹

```
你的影片總大小 > 200MB？
  ├─ 是 → 使用 YouTube
  └─ 否 → 繼續

你需要隱私控制（不想公開）？
  ├─ 是 → 使用 Google Drive 或 YouTube (不公開)
  └─ 否 → 繼續

你想要最快的載入速度？
  ├─ 是 → 使用 YouTube
  └─ 否 → 使用本地影片
```

### 各方案比較表

| 特性 | YouTube | Google Drive | 本地影片 |
|------|---------|--------------|----------|
| 免費容量 | 無限 | 15GB | 受 GitHub 限制 (1GB) |
| 載入速度 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| 隱私控制 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| 設定難度 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| 瀏覽器兼容 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| SEO 友善 | ⭐⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ |

---

## 📝 完整範例

### 範例 1: 三個專案使用不同影片來源

```html
<!-- 專案 1: YouTube -->
<article class="research-project">
    <div class="project-header">
        <h3>AI 品質預測系統</h3>
    </div>
    <div class="project-body">
        <div class="project-video-container">
            <div class="video-wrapper" data-video-type="youtube">
                <iframe
                    src="https://www.youtube.com/embed/YOUR_VIDEO_ID_1"
                    title="專案 1 示範影片"
                    frameborder="0"
                    allowfullscreen>
                </iframe>
            </div>
            <p class="video-caption">圖 1: 系統展示與效能指標</p>
        </div>
        <div class="project-details">
            <!-- 專案詳情 -->
        </div>
    </div>
</article>

<!-- 專案 2: Google Drive -->
<article class="research-project">
    <div class="project-header">
        <h3>視覺檢測系統</h3>
    </div>
    <div class="project-body">
        <div class="project-video-container">
            <div class="video-wrapper" data-video-type="gdrive">
                <iframe
                    src="https://drive.google.com/file/d/YOUR_FILE_ID_2/preview"
                    allow="autoplay">
                </iframe>
            </div>
            <p class="video-caption">圖 2: 即時瑕疵檢測示範 (60 FPS)</p>
        </div>
        <div class="project-details">
            <!-- 專案詳情 -->
        </div>
    </div>
</article>

<!-- 專案 3: 本地影片 -->
<article class="research-project">
    <div class="project-header">
        <h3>排程最佳化系統</h3>
    </div>
    <div class="project-body">
        <div class="project-video-container">
            <div class="video-wrapper" data-video-type="local">
                <video controls preload="metadata" poster="videos/scheduling-poster.jpg">
                    <source src="videos/scheduling-demo.mp4" type="video/mp4">
                    <source src="videos/scheduling-demo.webm" type="video/webm">
                    您的瀏覽器不支援影片播放。
                </video>
            </div>
            <p class="video-caption">圖 3: 演算法視覺化與效能比較</p>
        </div>
        <div class="project-details">
            <!-- 專案詳情 -->
        </div>
    </div>
</article>
```

---

## ❓ 常見問題

### Q1: YouTube 影片顯示「無法播放」
**A:** 檢查影片隱私設定：
1. 進入 YouTube Studio
2. 找到該影片
3. 確認設定為「公開」或「不公開」（不是「私人」）
4. 檢查是否有地區限制

### Q2: Google Drive 影片載入很慢
**A:** 這是正常的，解決方案：
1. 壓縮影片檔案（目標 < 50MB）
2. 降低解析度到 720p
3. 考慮改用 YouTube

### Q3: 本地影片無法播放
**A:** 檢查以下項目：
1. 檔案路徑是否正確（區分大小寫）
2. 影片格式是否為 MP4 (H.264)
3. 開啟瀏覽器開發者工具查看錯誤訊息
4. 確認檔案已上傳到 GitHub

### Q4: 影片在手機上無法自動播放
**A:** 這是正常的：
- 手機瀏覽器預設禁止影片自動播放
- 需要使用者點擊才能播放
- YouTube 和 Google Drive 影片不受影響

### Q5: 我可以混合使用三種方式嗎？
**A:** 可以！每個專案可以用不同的影片來源。例如：
- 專案 1、2 用 YouTube
- 專案 3 用 Google Drive
- 專案 4、5 用本地影片

---

## 🎬 影片製作建議

### 影片內容建議
1. **開場 (0-5 秒)**: 專案名稱 + 簡短標題
2. **主體 (5-60 秒)**: 系統運作展示
3. **結果 (60-90 秒)**: 成果數據圖表
4. **結尾 (可選)**: 聯絡資訊

### 技術規格建議
- **長度**: 60-120 秒最佳
- **解析度**: 1920x1080 或 1280x720
- **格式**: MP4 (H.264)
- **位元率**: 2-5 Mbps
- **音訊**: 如果有旁白，使用 AAC 128kbps

### 錄製工具推薦
- **螢幕錄製**:
  - Windows: OBS Studio (免費)
  - Mac: QuickTime Player (內建)
  - 跨平台: OBS Studio, ShareX
- **影片編輯**:
  - 初學者: DaVinci Resolve (免費)
  - 進階: Adobe Premiere Pro
- **壓縮工具**:
  - HandBrake (免費)
  - FFmpeg (命令列)

---

## 📊 效能優化建議

### 1. 使用影片懶加載

系統已內建影片懶加載功能：
- 影片只在進入視窗時才載入
- 節省頻寬和載入時間

### 2. 提供影片縮圖

為本地影片提供 poster 圖片：
```html
<video poster="videos/thumbnail.jpg">
```

### 3. 壓縮影片檔案

**目標檔案大小：**
- 60 秒影片：< 20MB
- 120 秒影片：< 40MB

**使用 HandBrake 壓縮：**
1. 開啟 HandBrake
2. 載入影片
3. 選擇 "Fast 1080p30" preset
4. Bitrate 設為 2000 kbps
5. 開始編碼

---

## ✅ 檢查清單

上線前確認：

- [ ] 所有 YouTube 影片 ID 已替換
- [ ] 所有 Google Drive 檔案 ID 已替換
- [ ] 本地影片檔案已上傳到 `videos/` 資料夾
- [ ] 影片在 Chrome 測試正常
- [ ] 影片在 Firefox 測試正常
- [ ] 影片在手機上測試正常
- [ ] 影片隱私設定正確（可公開觀看）
- [ ] 所有影片都有正確的 caption 說明

---

## 🚀 進階技巧

### 自訂播放器樣式

如果你想自訂本地影片播放器的樣式，可以修改 CSS：

```css
video {
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

video::-webkit-media-controls-panel {
    background-color: rgba(0, 0, 0, 0.5);
}
```

### YouTube 自動播放參數

讓 YouTube 影片自動播放（需要靜音）：

```html
<iframe
    src="https://www.youtube.com/embed/VIDEO_ID?autoplay=1&mute=1"
    ...>
</iframe>
```

### 多影片播放清單

如果一個專案有多個影片，可以這樣做：

```html
<div class="video-grid">
    <div class="video-wrapper">
        <iframe src="https://www.youtube.com/embed/VIDEO_1"></iframe>
    </div>
    <div class="video-wrapper">
        <iframe src="https://www.youtube.com/embed/VIDEO_2"></iframe>
    </div>
</div>
```

---

需要協助？在 GitHub Issues 提問或參考 README.md！

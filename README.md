# 學術作品集網站 Academic Portfolio

**研究機構專業風格** - 參考 Max Planck Institute 設計，專為申請國外碩士打造的學術作品集。

## 🌟 功能特色

- ✅ **研究機構專業風格** - 科學感、灰階配色、精緻排版
- ✅ **多種影片來源** - 支援 YouTube、Google Drive、本地影片
- ✅ **完整響應式設計** - 手機、平板、電腦完美顯示
- ✅ **進階動畫效果** - 平滑滾動、淡入、統計數字動畫
- ✅ **列印友善** - 教授可列印完整作品集
- ✅ **易於客製化** - 詳細文件與標註說明

## 📋 網站區塊

1. **Overview** - 個人簡介、研究興趣、統計數據、聯絡資訊
2. **Research Projects** - 產學案展示（支援影片嵌入）
3. **Publications** - 期刊論文列表（含 DOI、PDF、BibTeX）
4. **Patents** - 專利展示（已核准、審查中）
5. **Technical Expertise** - 技能條 + 技術標籤
6. **Contact** - 完整聯絡資訊與研究聲明

## 🎬 影片功能

系統支援三種影片來源，讓你靈活展示作品：

1. **YouTube** ⭐ 推薦
   - 無容量限制
   - 載入速度最快
   - 可設定「不公開」

2. **Google Drive**
   - 15GB 免費空間
   - 隱私控制佳
   - 適合不想用 YouTube 的情況

3. **本地影片**
   - 完全掌控
   - 無外部依賴
   - 適合小檔案 (< 50MB)

📖 **詳細使用方法請參考：[VIDEO_GUIDE.md](VIDEO_GUIDE.md)**

## 🚀 快速開始

### 方法 1: 直接在 GitHub 上使用

1. 在 GitHub 建立新倉庫，名稱為 `你的使用者名稱.github.io`
2. 將 `index.html`、`style.css`、`script.js` 上傳到倉庫
3. 進入 Settings → Pages，選擇 `main` 分支
4. 等待 1-2 分鐘，訪問 `https://你的使用者名稱.github.io`

### 方法 2: 本地開發

```bash
# 1. Clone 倉庫
git clone https://github.com/你的使用者名稱/你的使用者名稱.github.io.git
cd 你的使用者名稱.github.io

# 2. 複製檔案到倉庫目錄
# 將 index.html, style.css, script.js 複製進來

# 3. 本地預覽（雙擊 index.html 或使用本地伺服器）
# 推薦使用 Live Server 擴充功能（VS Code）

# 4. 上傳到 GitHub
git add .
git commit -m "Initial commit: Academic portfolio"
git push origin main
```

## ✏️ 客製化指南

### 1. 修改個人資訊

開啟 `index.html`，搜尋並替換以下內容：

```html
<!-- 姓名與標題 -->
<h1>張同學</h1>  <!-- 改成你的名字 -->
<h2>品質工程與人工智慧研究者</h2>  <!-- 改成你的專業領域 -->

<!-- 統計數字 -->
<div class="stat-number">5+</div>  <!-- 改成你的產學案數量 -->
<div class="stat-number">3</div>   <!-- 改成你的論文數量 -->
<div class="stat-number">2</div>   <!-- 改成你的專利數量 -->

<!-- 聯絡資訊 -->
<p>your.email@example.com</p>  <!-- 改成你的 Email -->
<a href="https://github.com/yourusername">  <!-- 改成你的 GitHub -->
```

### 2. 替換影片

找到產學案區塊，修改 YouTube 影片 ID：

```html
<!-- 原始示範影片 -->
<iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ"

<!-- 改成你的影片 -->
<iframe src="https://www.youtube.com/embed/你的影片ID"
```

**如何取得 YouTube 影片 ID？**
- YouTube 影片網址: `https://www.youtube.com/watch?v=ABC123XYZ`
- 影片 ID 就是: `ABC123XYZ`

**如何上傳影片到 YouTube？**
1. 登入 YouTube
2. 點擊右上角「建立」→「上傳影片」
3. 選擇「不公開」（只有有連結的人可看）
4. 上傳完成後，點擊「分享」→「嵌入」→ 複製 iframe 代碼

### 3. 修改專案內容

每個產學案包含以下部分：

```html
<div class="project-card">
    <!-- 影片區 -->
    <div class="project-video">...</div>

    <!-- 內容區 -->
    <div class="project-content">
        <h3>專案名稱</h3>  <!-- 改成你的專案名稱 -->
        <span class="project-year">2024</span>  <!-- 改成年份 -->

        <!-- 標籤 -->
        <div class="project-tags">
            <span class="tag">AI/ML</span>  <!-- 改成你的技術標籤 -->
            <span class="tag">品質工程</span>
        </div>

        <!-- 描述 -->
        <p class="project-description">
            這裡寫專案的詳細說明...
        </p>

        <!-- 成果數據 -->
        <div class="project-impact">
            <div class="impact-item">
                <strong>15%</strong>  <!-- 改成你的數據 -->
                <span>不良率降低</span>
            </div>
        </div>
    </div>
</div>
```

### 4. 修改論文清單

```html
<div class="publication-item">
    <div class="pub-year">2024</div>  <!-- 年份 -->
    <div class="pub-content">
        <h3>論文標題</h3>  <!-- 改成你的論文標題 -->
        <p class="pub-journal">期刊名稱, Vol. XX, pp. XX-XX</p>
        <p class="pub-authors"><strong>你的名字</strong>, 共同作者</p>
        <p class="pub-abstract">摘要...</p>

        <!-- 指標 -->
        <div class="pub-metrics">
            <span class="metric">IF: 8.3</span>  <!-- Impact Factor -->
            <span class="metric">Citations: 12</span>  <!-- 引用數 -->
            <span class="metric">Q1</span>  <!-- 期刊分區 -->
        </div>

        <!-- PDF 下載連結 -->
        <a href="你的PDF連結" class="btn-link">下載 PDF ↓</a>
    </div>
</div>
```

### 5. 修改專利

```html
<div class="patent-card">
    <div class="patent-icon">🔬</div>  <!-- 改成適合的 emoji -->
    <h3>專利名稱</h3>
    <p class="patent-number">專利號: TW I-XXXXXX</p>
    <p class="patent-status">
        <span class="status-badge granted">已核准</span>
        <!-- 或 -->
        <span class="status-badge pending">審查中</span>
    </p>
    <p class="patent-date">核准日期: 2024/03/15</p>
    <p class="patent-description">專利說明...</p>
</div>
```

### 6. 修改技能標籤

```html
<div class="skill-category">
    <h3>程式語言</h3>
    <div class="skill-items">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">你的技能</span>
        <!-- 新增更多標籤 -->
    </div>
</div>
```

## 🎨 修改配色

如果想改變網站配色，編輯 `style.css` 的 `:root` 區塊：

```css
:root {
    --primary-blue: #1e3a8a;      /* 主色（深藍） */
    --primary-light: #3b82f6;     /* 淺藍 */
    --accent-amber: #f59e0b;      /* 強調色（琥珀） */
    --accent-gold: #fbbf24;       /* 金色 */
}
```

**推薦配色方案：**
- **專業藍** (預設): `#1e3a8a` + `#f59e0b`
- **學術綠**: `#065f46` + `#f59e0b`
- **科技紫**: `#6b21a8` + `#f59e0b`
- **沉穩灰**: `#374151` + `#3b82f6`

## 📦 新增更多專案

複製整個 `project-card` 區塊：

```html
<!-- 複製這整段 -->
<div class="project-card">
    ...
</div>
<!-- 貼在其他專案下方 -->
```

## 🔧 進階功能

### 新增 Google Analytics

在 `</head>` 前加入：

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### 新增 Favicon

在 `<head>` 中加入：

```html
<link rel="icon" type="image/png" href="favicon.png">
```

### 新增自訂網域

1. 在倉庫根目錄建立 `CNAME` 檔案
2. 內容寫入: `www.yourdomain.com`
3. 在網域商設定 DNS 指向 GitHub Pages

## 📱 測試清單

上線前請確認：

- [ ] 所有個人資訊已替換
- [ ] 影片都能正常播放
- [ ] 所有連結都有效
- [ ] 在手機上測試過
- [ ] 在不同瀏覽器測試過（Chrome, Firefox, Safari）
- [ ] PDF 下載連結正確
- [ ] 聯絡資訊正確

## 💡 使用技巧

### 上傳 PDF 檔案

**方法 1: GitHub 直接上傳**
1. 在倉庫建立 `papers/` 資料夾
2. 上傳 PDF 檔案
3. 連結改為: `papers/your-paper.pdf`

**方法 2: 使用 Google Drive**
1. 上傳到 Google Drive
2. 設定為「知道連結的任何人」
3. 取得分享連結
4. 連結改為: `https://drive.google.com/file/d/FILE_ID/view`

### 處理大量影片

如果有很多影片：
1. 建立 YouTube 播放清單
2. 設定為「不公開」
3. 在網站只放重要影片
4. 其他影片放連結到播放清單

## 🐛 常見問題

**Q: 為什麼影片不顯示？**
- 確認影片是「公開」或「不公開」（不是「私人」）
- 檢查影片 ID 是否正確
- 確認沒有廣告攔截器干擾

**Q: 手機版選單無法點擊？**
- 檢查 `script.js` 是否正確載入
- 清除瀏覽器快取

**Q: 網站更新後沒變化？**
- 清除瀏覽器快取（Ctrl+F5）
- 等待 GitHub Pages 重新部署（1-2 分鐘）

**Q: 如何加密碼保護？**
- GitHub Pages 免費版不支援密碼保護
- 建議使用 Netlify 或 Vercel（支援密碼保護）

## 📚 延伸資源

- [GitHub Pages 官方文件](https://docs.github.com/en/pages)
- [Markdown 語法](https://www.markdownguide.org/)
- [YouTube 嵌入教學](https://support.google.com/youtube/answer/171780)
- [HTML 顏色代碼](https://htmlcolorcodes.com/)

## 📄 授權

此模板免費使用，無需標註來源。祝申請順利！🎓

---

**需要協助？** 在 GitHub Issues 提問或聯絡我。
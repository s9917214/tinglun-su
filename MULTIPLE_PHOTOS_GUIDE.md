# 📸 多张照片展示指南

这份指南将教您如何展示多张获奖照片，让您的 Awards 部分更加生动精彩！

## 🎯 已为您实现的两种方案

### ✅ 方案 1：自动轮播图（已应用于 2025 年奖项）

**效果：**
- 📸 照片自动切换（每5秒）
- ← → 左右箭头手动切换
- ⚫ 底部小圆点显示当前位置
- 🖱️ 点击圆点直接跳转

**文件夹结构：**
```
images/
└── awards/
    └── 2025/
        ├── photo1.jpg    ← 主要照片
        ├── photo2.jpg    ← 第二张
        └── photo3.jpg    ← 第三张
```

**照片建议：**
- 数量：2-5 张最佳
- 尺寸：800x600 或更大
- 内容：颁奖现场、奖杯、团队合照、证书特写等

---

### ✅ 方案 2：图片拼贴（已应用于 2024 年奖项）

**效果：**
- 📸 左侧一张大图
- 📸 右侧两张小图
- 🖱️ 悬停时图片放大

**文件夹结构：**
```
images/
└── awards/
    └── 2024/
        ├── award1.jpg    ← 左侧大图（最重要的照片）
        ├── award2.jpg    ← 右上小图
        └── award3.jpg    ← 右下小图
```

**照片建议：**
- 数量：固定 3 张
- 尺寸：800x600 或更大
- 大图：最重要的照片（颁奖现场、第一名奖杯等）
- 小图：补充照片（证书、团队、活动现场等）

---

## 📂 完整的文件夹组织方案

### 推荐结构（按年份组织）：

```
TingLun-SU_Allen/
├── index.html
├── style.css
├── script.js
└── images/
    ├── profile.jpg                    ← 个人头像
    └── awards/
        ├── 2025/                      ← 2025年奖项照片
        │   ├── photo1.jpg
        │   ├── photo2.jpg
        │   └── photo3.jpg
        ├── 2024/                      ← 2024年奖项照片
        │   ├── award1.jpg
        │   ├── award2.jpg
        │   └── award3.jpg
        ├── 2023/                      ← 2023年奖项照片
        │   ├── tdk1.jpg
        │   ├── tdk2.jpg
        │   └── tdk3.jpg
        └── early/                     ← 2020-2022早期成就
            ├── medal1.jpg
            ├── medal2.jpg
            └── medal3.jpg
```

---

## 🎨 选择方案的建议

### 什么时候用**轮播图**？
✅ 有 3-5 张**同类**照片（例如：同一个活动的不同角度）
✅ 想展示完整的颁奖流程（报到 → 展示 → 颁奖 → 合照）
✅ 希望页面更有动态感
✅ 照片质量都很高，每张都想重点展示

**示例：**
- 2025年全国竞赛：报到照、作品展示、颁奖瞬间、团队合照、证书特写

### 什么时候用**拼贴**？
✅ 有 2-3 张照片，其中有一张特别重要
✅ 想一次性展示多个角度
✅ 希望布局更紧凑简洁
✅ 有一张"主角照片" + 几张补充照片

**示例：**
- 2024年自动化大奖：
  - 大图：捧着金奖奖杯的照片
  - 小图1：颁奖现场
  - 小图2：获奖证书

### 什么时候用**单张照片**？
✅ 只有 1-2 张照片
✅ 照片质量极高，不需要其他补充
✅ 希望保持简洁专业

---

## 🔧 如何应用到其他年份？

### 方法 1：为 2023 年添加轮播图

在 `index.html` 中找到 2023 年的照片部分，替换为：

```html
<div class="award-photo">
    <div class="photo-carousel">
        <div class="carousel-images">
            <img src="images/awards/2023/tdk1.jpg" alt="TDK Cup Photo 1" class="carousel-img active">
            <img src="images/awards/2023/tdk2.jpg" alt="TDK Cup Photo 2" class="carousel-img">
            <img src="images/awards/2023/tdk3.jpg" alt="TDK Cup Photo 3" class="carousel-img">
        </div>
        <button class="carousel-btn prev" onclick="changeSlide(this, -1)">‹</button>
        <button class="carousel-btn next" onclick="changeSlide(this, 1)">›</button>
        <div class="carousel-dots">
            <span class="dot active" onclick="currentSlide(this, 0)"></span>
            <span class="dot" onclick="currentSlide(this, 1)"></span>
            <span class="dot" onclick="currentSlide(this, 2)"></span>
        </div>
    </div>
    <p class="photo-caption">TDK Cup Award Ceremony 2023</p>
</div>
```

**重要：** 有几张照片就添加几个：
- `<img>` 标签
- `<span class="dot">` 标签（数量要一致）

---

### 方法 2：为早期成就添加拼贴

在 `index.html` 中找到 2020-2022 的照片部分，替换为：

```html
<div class="award-photo">
    <div class="photo-grid">
        <img src="images/awards/early/medal1.jpg" alt="Early Achievement 1" class="grid-img main">
        <div class="grid-side">
            <img src="images/awards/early/medal2.jpg" alt="Early Achievement 2" class="grid-img">
            <img src="images/awards/early/medal3.jpg" alt="Early Achievement 3" class="grid-img">
        </div>
    </div>
    <p class="photo-caption">National Science Fair Competitions 2020-2022</p>
</div>
```

---

## 📝 照片命名建议

### 清晰的命名方式：

**按年份 + 序号：**
```
2025/
├── photo1.jpg
├── photo2.jpg
└── photo3.jpg
```

**按内容描述：**
```
2024/
├── first-place-trophy.jpg
├── award-ceremony.jpg
└── team-photo.jpg
```

**按活动流程：**
```
2023/
├── registration.jpg
├── presentation.jpg
├── award-moment.jpg
└── group-photo.jpg
```

---

## 🎯 照片准备检查清单

准备照片时，检查这些要点：

### 照片质量
- [ ] 分辨率至少 800x600
- [ ] 光线充足，画面清晰
- [ ] 主题明确（避免模糊、背光）
- [ ] 横向照片（4:3 或 16:9 比例）

### 照片内容
- [ ] **照片1（主要）：** 颁奖瞬间或奖杯特写
- [ ] **照片2（补充）：** 团队合照或活动现场
- [ ] **照片3（可选）：** 证书特写或作品展示
- [ ] **照片4-5（可选）：** 其他精彩瞬间

### 照片处理
- [ ] 文件大小 < 500KB（使用 TinyPNG 压缩）
- [ ] 格式为 JPG 或 PNG
- [ ] 文件名正确（不含空格、特殊字符）
- [ ] 已放入正确的文件夹

---

## 💡 专业建议

### 1. **照片故事性**
按照时间顺序排列照片，讲述获奖的完整故事：
- 轮播顺序：准备 → 展示 → 颁奖 → 庆祝
- 拼贴布局：大图（最重要瞬间） + 小图（前后补充）

### 2. **照片一致性**
同一年份的照片建议：
- 同一个活动或场合
- 色调和风格相近
- 避免风格混杂

### 3. **照片数量**
- **轮播图：** 3-5 张最佳（太多会分散注意力）
- **拼贴：** 固定 3 张（1大2小）
- **单张：** 精选最好的 1 张

### 4. **照片优先级**
如果照片很多，优先选择：
1. ⭐⭐⭐ 举起奖杯的瞬间
2. ⭐⭐⭐ 颁奖现场（与颁奖嘉宾合照）
3. ⭐⭐ 团队合照
4. ⭐⭐ 证书/奖状特写
5. ⭐ 作品展示或活动现场

---

## 🆘 常见问题

### Q1: 我有10张照片，能全部展示吗？
**A:** 不建议。太多照片会让页面冗长，失去焦点。
- **最佳做法：** 精选 3-5 张最好的照片
- **替代方案：** 可以考虑做一个外部相册链接

### Q2: 照片数量不一样怎么办？
**A:**
- **2 张照片：** 使用拼贴，删除第3张小图的代码
- **4 张照片：** 使用轮播图
- **1 张照片：** 使用单张展示（目前的默认方式）

### Q3: 可以混合使用两种方案吗？
**A:** 可以！
- 2025年：轮播图（5张照片）
- 2024年：拼贴（3张照片）
- 2023年：单张（1张照片）
- 早期成就：拼贴（3张照片）

### Q4: 轮播图不自动播放怎么办？
**A:** 检查：
1. `script.js` 文件是否正确加载
2. 浏览器控制台是否有错误（按 F12 查看）
3. 照片路径是否正确

### Q5: 照片变形怎么办？
**A:** 使用 `object-fit: cover` 已自动处理。如果还是变形：
- 确保照片比例接近 4:3
- 使用图片编辑工具裁剪成 4:3 比例

---

## 🚀 快速开始

### 步骤 1：创建文件夹
```bash
mkdir -p images/awards/2025
mkdir -p images/awards/2024
mkdir -p images/awards/2023
mkdir -p images/awards/early
```

### 步骤 2：准备照片
- 收集每个年份的 2-5 张最佳照片
- 重命名为 `photo1.jpg`, `photo2.jpg` 等
- 使用 TinyPNG 压缩（< 500KB）

### 步骤 3：上传照片
- 将照片复制到对应文件夹
- 确认文件名正确

### 步骤 4：刷新查看
- 按 `Ctrl + F5` 强制刷新浏览器
- 查看轮播图和拼贴效果

---

## 📸 推荐的照片组合示例

### 2025年全国竞赛（轮播5张）：
1. 作品展示台
2. 项目讲解瞬间
3. 评委提问环节
4. 颁奖瞬间（举起奖杯）
5. 团队合照

### 2024年自动化大奖（拼贴3张）：
- 大图：第一名奖杯特写
- 小图1：颁奖台上的瞬间
- 小图2：获奖证书

### 2023年TDK杯（轮播3张）：
1. 创意作品展示
2. 颁奖现场
3. 获奖证书 + 奖杯

### 早期成就（拼贴3张）：
- 大图：金牌展示
- 小图1：银牌展示
- 小图2：科展现场

---

需要更多帮助？告诉我您有多少张照片，我可以帮您选择最合适的展示方式！

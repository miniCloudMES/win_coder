# Win_Coder - MES 專業網頁設計

🏭 專業製造執行系統 (MES) Landing Page 設計方案

## 專案簡介

這是一個為 MES (Manufacturing Execution System) 系統設計的專業著陸頁 (Landing Page)，提供現代化、響應式的網頁界面，適合製造業數位轉型需求。

## 功能特色

### 🎯 核心功能展示
- **即時監控** - 生產狀態、設備運行狀況和品質指標追蹤
- **生產排程** - 智能排程演算法優化生產順序
- **品質管理** - 完整的品質控制流程
- **成本控制** - 精確計算物料消耗和人工成本
- **追溯系統** - 完整的產品追溯能力
- **數據分析** - 強大的數據分析和決策支援

### 📱 技術特點
- ✅ 響應式設計 (RWD) - 支援桌面、平板、手機
- ✅ 現代化 UI 設計 - 漸層色彩、流暢動畫
- ✅ 平滑滾動導航
- ✅ 即時時間更新顯示
- ✅ 表單驗證功能
- ✅ 無需外部依賴 - 單一 HTML 文件即可運行

## 適用產業

- 📱 電子製造 (SMT、PCB、半導體)
- 🚗 汽車工業 (零組件製造、組裝線)
- 💊 生技醫藥 (藥品、醫療器材)
- 👕 紡織成衣 (布料、服飾製造)
- 🥫 食品加工 (食品安全追溯)
- 🏠 精密機械 (金屬加工、模具)

## 快速開始

### 本地預覽

直接雙擊 `mes_landing_page.html` 文件即可在瀏覽器中查看效果：

```bash
# Windows
start mes_landing_page.html

# macOS
open mes_landing_page.html

# Linux
xdg-open mes_landing_page.html
```

### 使用本地伺服器

```bash
# 使用 Python
python -m http.server 8000

# 使用 Node.js
npx http-server

# 然後訪問 http://localhost:8000
```

## 頁面結構

```
mes_landing_page.html
├── Header (導航欄)
├── Hero Section (主視覺區)
├── Features (核心功能)
├── Dashboard Preview (儀表板預覽)
├── Industries (適用產業)
├── Testimonials (客戶見證)
├── Contact Form (聯絡表單)
└── Footer (頁腳)
```

## 自定義指南

### 修改配色方案

在 `<style>` 區塊中找到顏色變數：

```css
/* 主色調 */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* 強調色 */
.cta-button {
    background: #ff6b6b;
}
```

### 修改公司資訊

在 Footer 區塊更新聯絡資訊：

```html
<div class="footer-section">
    <h3>聯絡資訊</h3>
    <ul class="footer-links">
        <li>📞 (02) 1234-5678</li>
        <li>✉️ info@promes.com.tw</li>
        <li>🏢 台北市內湖區文德路 200 號</li>
    </ul>
</div>
```

### 添加新功能卡片

在 Features Section 中添加新的 feature-card：

```html
<div class="feature-card">
    <div class="feature-icon">🔧</div>
    <h3>新功能名稱</h3>
    <p>功能描述...</p>
</div>
```

## 技術規格

| 項目 | 規格 |
|------|------|
| HTML 版本 | HTML5 |
| CSS 版本 | CSS3 (Flexbox, Grid) |
| JavaScript | Vanilla JS (ES6+) |
| 瀏覽器支援 | Chrome, Firefox, Safari, Edge |
| 文件大小 | ~20KB |
| 外部依賴 | 無 |

## 專案結構

```
win_coder/
├── README.md              # 專案說明文件
├── mes_landing_page.html  # MES 著陸頁主文件
└── (其他專案文件)
```

## 開發者資訊

- **專案名稱**: Win_Coder
- **版本**: 1.0.0
- **授權**: MIT License
- **聯絡**: info@promes.com.tw

## 更新日誌

### v1.0.0 (2024-02-19)
- ✨ 初始版本發布
- 🎨 完整 Landing Page 設計
- 📱 響應式設計支援
- 📝 聯絡表單功能
- 📊 儀表板預覽展示

## 貢獻指南

歡迎提交 Issue 和 Pull Request！

1. Fork 本專案
2. 創建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交變更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

## 授權條款

本專案採用 MIT 授權條款 - 詳見 [LICENSE](LICENSE) 文件

---

<p align="center">
  <strong>🏭 ProMES - 智慧製造執行系統</strong><br>
  提升生產效率 · 優化資源配置 · 實現即時監控
</p>

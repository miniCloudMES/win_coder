# ProMES Dashboard 2.0 - Vue 3 現代化版本

🚀 使用 Vue 3 + Tailwind CSS + Chart.js 打造的現代化 MES 儀表板

## ✨ 新特性

### 技術棧升級
- **Vue 3** - 最新 Composition API，更好的性能
- **Tailwind CSS** - 實用優先的 CSS 框架
- **Chart.js** - 專業的數據可視化
- **Font Awesome** - 豐富的圖標庫

### 功能改進
- 🎨 **現代化 UI 設計** - 漸層色彩、卡片陰影、流暢動畫
- 📊 **互動式圖表** - 支援切換日/週/月視圖
- 🔔 **即時警報系統** - 視覺化警報提示
- 📱 **完全響應式** - 支援桌面、平板、手機
- ⚡ **即時數據更新** - 模擬 WebSocket 即時連線
- 🎯 **KPI 指標卡片** - 關鍵績效指標一目瞭然

## 📁 專案結構

```
win_coder/
├── mes_landing_page.html      # 產品著陸頁 (v1.0)
├── mes_dashboard.html         # 傳統儀表板 (v1.0)
├── mes_dashboard_vue.html     # Vue 3 儀表板 (v2.0) ⭐
├── package.json               # 專案配置
├── README.md                  # 專案說明
└── README_VUE.md             # Vue 版本說明
```

## 🚀 快速開始

### 方式一：直接開啟 HTML（推薦）

無需安裝任何依賴，直接雙擊開啟：

```bash
# Windows
start mes_dashboard_vue.html

# macOS
open mes_dashboard_vue.html

# Linux
xdg-open mes_dashboard_vue.html
```

### 方式二：使用本地伺服器

```bash
# 使用 Node.js
npm install -g http-server
http-server -p 3000

# 或使用 Python
python -m http.server 8000

# 然後訪問 http://localhost:3000/mes_dashboard_vue.html
```

### 方式三：完整開發環境（進階）

```bash
# 安裝依賴
npm install

# 啟動開發伺服器
npm run dev

# 構建生產版本
npm run build
```

## 🎯 核心功能

### 1. KPI 指標卡片
- 設備綜合效率 (OEE)
- 今日產量
- 良品率
- 不良率
- 即時趨勢對比

### 2. 生產趨勢分析
- 即時生產數據
- 目標 vs 實際對比
- 日/週/月視圖切換
- 平滑曲線圖表

### 3. 品質分析
- 良品率圓餅圖
- 不良類型分類
- 製程別分析
- 互動式圖例

### 4. 生產線監控
- 即時狀態顯示
- 達成率進度條
- 顏色編碼狀態
- 快速操作入口

### 5. 即時警報
- 緊急警報（紅色）
- 警告提示（黃色）
- 資訊通知（藍色）
- 快速處理按鈕

### 6. 訂單進度追蹤
- 多訂單同時監控
- 進度條視覺化
- 預計完成時間
- 剩餘數量顯示

## 🎨 自定義指南

### 修改主題色彩

在 HTML 中找到 Tailwind 配置：

```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                primary: '#667eea',    // 主色調
                secondary: '#764ba2',  // 次要色
                success: '#48bb78',    // 成功色
                warning: '#ecc94b',    // 警告色
                danger: '#f56565',     // 危險色
                info: '#4299e1'        // 資訊色
            }
        }
    }
}
```

### 添加新的 KPI 指標

在 Vue 數據中添加：

```javascript
kpiData: [
    {
        id: 5,
        title: '新指標名稱',
        value: '數值',
        trend: 2.5,
        icon: 'fas fa-icon-name',
        borderClass: 'border-primary',
        bgClass: 'gradient-primary'
    }
]
```

### 修改側邊欄選單

```javascript
mainMenu: [
    { id: 'new-menu', label: '新功能', icon: 'fas fa-star', href: '#' }
]
```

### 整合真實 API

替換 `refreshData()` 方法：

```javascript
async refreshData() {
    try {
        const response = await axios.get('/api/mes/dashboard');
        this.kpiData = response.data.kpi;
        this.productionLines = response.data.lines;
        // ... 更新其他數據
    } catch (error) {
        console.error('數據載入失敗:', error);
    }
}
```

## 📊 API 整合範例

### 後端 API 結構建議

```javascript
// GET /api/mes/dashboard
{
    "timestamp": "2024-02-19T14:00:00Z",
    "kpi": {
        "oee": 87.5,
        "production": 2847,
        "quality": 98.8,
        "defect": 1.2
    },
    "lines": [
        {
            "id": 1,
            "name": "生產線 A",
            "status": "running",
            "target": 1000,
            "actual": 987
        }
    ],
    "alerts": [
        {
            "id": 1,
            "level": "critical",
            "message": "生產線 C 緊急停機",
            "timestamp": "2024-02-19T13:50:00Z"
        }
    ]
}
```

### WebSocket 即時更新

```javascript
// 在 mounted 中添加
const ws = new WebSocket('ws://your-server.com/mes');
ws.onmessage = (event) => {
    const data = JSON.parse(event.data);
    this.updateDashboard(data);
};
```

## 🔧 技術規格

| 項目 | 規格 |
|------|------|
| Vue 版本 | 3.4.x |
| Tailwind CSS | 3.4.x |
| Chart.js | 4.4.x |
| 瀏覽器支援 | Chrome, Firefox, Safari, Edge (最新版) |
| 響應式 | 支援 Mobile, Tablet, Desktop |
| 外部依賴 | CDN 載入（無需構建） |

## 🆚 版本比較

| 功能 | v1.0 (HTML) | v2.0 (Vue) |
|------|-------------|------------|
| 框架 | 純 HTML/CSS/JS | Vue 3 |
| 樣式 | 自定義 CSS | Tailwind CSS |
| 圖表 | CSS 模擬 | Chart.js |
| 數據綁定 | 手動 DOM | 響應式 |
| 組件化 | ❌ | ✅ |
| API 整合 | 手動 | Axios 支援 |
| 可維護性 | 中 | 高 |

## 📝 更新日誌

### v2.0.0 (2024-02-19)
- ✨ 使用 Vue 3 重構整個儀表板
- 🎨 採用 Tailwind CSS 現代化設計
- 📊 整合 Chart.js 專業圖表
- 🔔 改進警報系統視覺效果
- 📱 優化響應式設計
- ⚡ 添加即時數據更新模擬
- 🎯 改進 KPI 卡片設計

### v1.0.0 (2024-02-19)
- ✨ 初始版本發布
- 📊 基本儀表板功能
- 📱 響應式設計

## 🤝 貢獻指南

歡迎提交 Issue 和 Pull Request！

1. Fork 本專案
2. 創建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交變更 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

## 📄 授權條款

本專案採用 MIT 授權條款

## 📞 聯絡資訊

- **專案**: ProMES 智慧製造系統
- **版本**: 2.0.0
- **技術支援**: support@promes.com.tw

---

<p align="center">
  <strong>🏭 ProMES - 智慧製造執行系統</strong><br>
  提升生產效率 · 優化資源配置 · 實現即時監控
</p>

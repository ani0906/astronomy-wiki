# AGENTS.md — 先鋒藝術天文誌 (Avant-Garde Editorial Astronomy Wiki) 維護規範

本文件為「天文知識小百科」專案的最高維護準則（Schema）。任何協助整理、擴充或維護本知識庫的 LLM Agent 都必須嚴格遵守以下視覺設計哲學、雙層分類架構、筆記模板與獨立網頁發布規範。

---

## 1. 核心哲學 (Core Philosophy: LLM Wiki + Avant-Garde Editorial)

本專案結合 **Andrej Karpathy 的 LLM Wiki Pattern** 與 **瑞士平面設計 (Swiss Graphic Design / International Typographic Style)** 的前衛藝術刊物排版：
1. **知識持續累積與編譯**：所有原始資料原封不動存於 `raw/`，LLM 萃取編譯至 `wiki/` 結構化 Markdown 筆記中，維護雙向鏈接與歷史脈絡。
2. **高張力先鋒視覺體驗**：打破一般單調死板的百科樣式，全面採用高對比、極致字體張力、外露黑色網格與幾何裁切遮罩的**先鋒藝術天文誌**風格。
3. **純靜態獨立發布**：每次新增文章時，在 `pages/` 生成獨立 HTML 網頁，引入中央樣式表 `assets/style.css`，並同步更新總目錄 `index.md` 與首頁 `index.html`。

---

## 2. 先鋒藝術視覺系統規範 (Visual Design System)

所有前端網頁（`index.html` 與 `pages/*.html`）皆統一引用 `assets/style.css`（內頁使用 `../assets/style.css`），並嚴格落實以下視覺規範：

### 2.1 高張力色彩系統 (High-Tension Color Palette)
* **美術館紙張底色 (Museum Paper White)**：`#F4F3EF` — 溫潤具質感的紙張底色，全站背景附帶細膩的微雜訊紙張顆粒質感（Paper Grain）。
* **極黑墨色 (Pitch Black)**：`#0D0D0D` — 所有文字、外露 1px 網格分割線、邊框與硬陰影。
* **高飽和電光鈷藍 (Electric Cobalt Blue)**：`#1A4BFF` — 核心主視覺、按鈕互動高亮、超大號編輯編號與重點數據標註。
* **微螢光青 (Fluorescent Cyan)**：`#00F0FF` — 首頁海報殘影字跡的錯位疊色。
* **次級說明墨灰 (Muted Ink)**：`#5A5A5A` — 出處、副標題與次級說明文字。

### 2.2 極端字體張力 (Typography Tension via Google Fonts)
* **超大主標題**：採用高聳窄體 **`Anton`** 搭配 **`Noto Serif TC`**，設定緊湊行距（`line-height: 0.9 ~ 0.95`），字體縮放配合 `clamp()` 呈現海報級視覺震撼。
* **副標題與引文**：混搭 **`Playfair Display`** 斜體，營造高端藝術刊物的優雅對比。
* **微標註與技術數據**：一律採用等寬字體 **`Space Mono`** 呈現日期、分類標籤、物理參數數值與檔案代號。
* **正文內文**：採用 **`Noto Serif TC`**（襯線字體），行高 `1.8`，維持絕佳的長篇閱讀體驗。

### 2.3 雜誌跨頁網格與細節 (Swiss Grid & Editorial Details)
* **外露黑色網格 (Exposed 1px Grid)**：所有區塊之間以 `1px solid #0D0D0D` 線條清晰分割，無任何圓角邊框（`border-radius: 0px`），保持純粹瑞士網格秩序。
* **期刊頁眉 (Masthead)**：頁面頂部附帶微型黑底期刊條：
  `VOL.01 // ASTRONOMICAL ENCYCLOPEDIA // TAEA ARCHIVE // 2026`
* **幾何裁切遮罩 (Geometric Mask & Interaction)**：文章圖片必須使用幾何多邊形裁切遮罩（如八角切角 `clip-path: polygon(...)`），滑鼠懸停時由微反差灰階平滑過渡至全彩高對比，並伴隨電光藍硬陰影浮動效果。
* **SVG 無死角補位**：若本地無對應真實圖檔，必須在網頁中內建高精度向量 SVG 科學示意圖，杜絕破圖。

### 2.4 【重大原則】首頁藝術拼貼 vs. 內頁純淨排版規範
為兼顧首頁的視覺衝擊力與內文的絕佳閱讀性，嚴格實行分層設計原則：

1. **首頁限定視覺拼貼（僅限 `index.html`，嚴禁出現在 `pages/` 閱讀區）**：
   * **層疊殘影字跡 (Layered Ghosting Typography)**：在首頁 Hero 視覺右側加入由下往上延伸的層疊重複字樣（`OBSERVE * COSMOS`），做出多層錯位、微螢光青與鈷藍疊色的海報殘影視覺。
   * **斜切鈷藍口袋拼貼 (Slanted Cobalt Blue Pocket)**：在首頁 Hero 視覺焦點設計一個斜切角度的 `#1A4BFF` 紙質口袋層，讓一張帶米白相框的天文照片從口袋探出半截，口袋左下角壓上白色粗體標籤（`ASTRONOMICAL ARCHIVE`）與右下角年份（`2026`）。
   * **跨框重疊超大編號 (Cross-Border Overlapping Numbers)**：首頁文章卡片上的巨大編號（`01`、`02`、`03`...）向上跨越卡片頂部邊框線，形成半重疊在卡片上沿的藝術畫冊排版。
2. **內頁純淨原則（`pages/` 獨立文章頁面）**：
   * **嚴格禁止**在 `pages/` 底下的內頁加入層疊殘影字跡、斜切口袋或阻礙長篇閱讀的裝飾拼貼。
   * 內頁必須保持清爽俐落的瑞士雙欄網格排版（主論述區 + 側邊數據微標註），讓讀者專注於高品質圖文、精確數據表格與原理解析。

---

## 3. 目錄架構 (Project Architecture)

```text
LLM Wiki 工作資料夾/
├── AGENTS.md                  # 【規範層】Agent 運行規則、視覺標準（本檔案）
├── index.md                   # 【索引層】Markdown 總目錄（依五大分類組織）
├── log.md                     # 【日誌層】時間戳追加紀錄（Ingest / Query / Lint）
├── index.html                 # 【展示層·首頁】海報拼貼首頁（斜切口袋、殘影疊字、跨框編號）
│
├── assets/                    # 【靜態資源層】
│   ├── style.css              # 🎨 中央樣式表（含紙張顆粒質感、拼貼元件、雙欄排版）
│   └── images/                # 本地高清天文圖片
│
├── pages/                     # 【靜態獨立展示頁層（GitHub Pages）】— 保持純淨排版
│   ├── solar-system-structure.html # 太陽系結構與範圍（純淨雙欄、SVG 尺度圖）
│   ├── sun.html               # 太陽（SDO 極紫外圖、黑子實測、剖面圖）
│   └── planet-definition-and-dwarf-planets.html # 行星定義與矮行星分類（IAU 決策樹）
│
├── raw/                       # 【第一層：原始資料庫（Immutable 唯讀）】
│   ├── articles/              # 原始科普貼文全文
│   ├── docs/                  # 論文、PDF 或長篇文字檔案
│   └── images/                # 原始下載圖檔
│
└── wiki/                      # 【第二層：結構化知識庫（Markdown）】
    ├── solar_system/          # 太陽系與行星科學
    ├── exoplanets/            # 系外行星與適居帶
    ├── stellar_evolution/     # 恆星演化與緻密天體
    ├── galaxies_cosmology/    # 星系結構與宇宙學
    ├── observation_missions/  # 天文觀測與太空任務
    └── sources/               # 原始文獻消化精讀筆記
```

---

## 4. 百科雙層分類架構 (Category Architecture)

每篇收錄的條目必須明確歸入以下 **主分類 > 次分類** 之一，並附帶 **2～3 個關鍵字標籤**：

1. **太陽系與行星科學 (`solar_system`)**：
   * 類地行星與類木行星
   * 衛星與矮行星
   * 太陽系小天體
2. **系外行星與適居帶 (`exoplanets`)**：
   * 系外行星類型
   * 偵測與觀測方法
   * 適居帶與大氣特徵
3. **恆星演化與緻密天體 (`stellar_evolution`)**：
   * 恆星生命週期
   * 超新星與緻密殘骸
   * 雙星系統與高能現象
4. **星系結構與宇宙學 (`galaxies_cosmology`)**：
   * 星系分類與構造
   * 星系團與大尺度結構
   * 宇宙起源與演化
5. **天文觀測與太空任務 (`observation_missions`)**：
   * 地面望遠鏡與多波段觀測
   * 太空望遠鏡與深空探測器

---

## 5. 單篇 `wiki/` 筆記固定 7 大區塊模板

所有在 `wiki/` 資料夾下建立的 Markdown 筆記，必須嚴格依照以下 7 大區塊架構撰寫：

```markdown
---
title: "天體或主題名稱"
main_category: "主分類名稱"
sub_category: "次分類名稱"
tags: [關鍵字1, 關鍵字2, 關鍵字3]
last_updated: "YYYY-MM-DD"
image: "assets/images/<filename>.jpg"
---

# 天體或主題名稱

> **主分類**：主分類名稱 > **次分類**：次分類名稱  
> **標籤**：`#標籤1` `#標籤2` `#標籤3`

---

## 📖 主題導言
（2～3 句自然科普文字，概述核心物理定位與天文意義。）

---

## 🖼️ 視覺圖解
![圖片標題](assets/images/<filename>.jpg)
*圖說：詳細闡述該圖所展示之物理結構、波段或對比尺度。*

---

## 📊 物理與觀測檔案
| 關鍵項目 | 參數數值 / 物理特徵 | 備註說明 |
| :--- | :--- | :--- |
| **參數名稱** | 數值 | 說明 |

---

## 🔬 科學原理解析
* **分點一**：詳細闡釋動力學或物理機制。
* **分點二**：詳細闡釋輻射或光譜特徵。
* **分點三**：詳細闡釋演化或環境相互作用。

---

## 🌌 代表天體與觀測案例
1. **案例一**：觀測年代、探測器或天文事件。
2. **案例二**：對比案例或歷史意義。

---

## 🔗 相關條目連結
* [[wiki/路徑/條目名|相關條目名稱]]
* [[wiki/sources/文獻名|來源精讀]]
```

---

## 6. 網頁發布與獨立 HTML 生成規範 (Web Output Rules)

每次在 `wiki/` 新增或修改文章時：
1. **獨立 HTML 生成 (`pages/<article-id>.html`)**：
   * 引用 `../assets/style.css`。
   * 頂部加入微型標頭：`VOL.01 // ASTRONOMICAL ENCYCLOPEDIA // 2026`。
   * 標題橫幅配置超大號編輯編號（如 `01`、`02`）與 `Anton` 巨型標題。
   * 內文採用純淨雜誌雙欄網格（主論述區 + 側邊數據微標註），**絕不加入殘影疊字或斜切遮擋**。
   * 圖片套用八角幾何切角（`art-image-frame`）與電光藍硬陰影。
   * 內建高精度向量 SVG 圖解，避免破圖。
2. **首頁動態更新 (`index.html`)**：
   * 引用 `assets/style.css`。
   * 配備斜切口袋、探出相框、殘影字跡三大拼貼焦點。
   * 條目卡片配置跨框重疊索引數字（`editorial-idx-overlap`）。
3. **總目錄與日誌同步**：更新 `index.md` 與追加 `log.md`。

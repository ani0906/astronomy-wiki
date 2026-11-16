# 天文知識小百科 維護日誌 (Log)

本檔案採用時間順序追加記錄（Append-only），記錄所有文獻攝入 (Ingest)、深度查詢與綜述 (Query)、以及健康檢查 (Lint)。

---

## [2026-11-16] init | 初始化天文知識小百科架構
* **操作類型**：系統初始化
* **建立目錄**：
  * `raw/`（`articles/`, `docs/`, `images/`）
  * `wiki/`（`solar_system/`, `stars/`, `galaxies/`, `phenomena/`, `observation/`, `sources/`）
* **建立規範與索引**：
  * `AGENTS.md`：定義 Karpathy LLM Wiki 運作 SOP、Frontmatter 與 GitHub Pages 規範
  * `index.md`：建立主題分類目錄
  * `log.md`：建立維護歷史紀錄
  * `index.html` & `data.js`：建立純前端星空主題展示網頁（支援 GitHub Pages 與本機雙擊開啟）
* **初始示範條目**：
  * `wiki/solar_system/sun.md`：太陽核心參數與結構介紹


## [2026-11-16] ingest | 太陽系結構與範圍 (臺南市南瀛天文館)
* **原始來源**：https://taea.tn.edu.tw/astro_news/book_detail/e19f5986-0d31-11eb-9294-9c5415e2e998
* **存檔文件**：`raw/solar_system.md`、`raw/articles/solar_system.md`
* **下載資源**：`assets/images/solar_system_planets.jpg`、`assets/images/solar_system_boundary.jpg`
* **建立/更新條目**：
  * `wiki/solar_system/solar-system-structure.md`：符合 7 大區塊標準模板
  * `wiki/sources/taea-solar-system.md`：原始文獻精讀摘要
  * `pages/solar-system-structure.html`：獨立靜態展示網頁（含太陽系空間尺度科學向量 SVG 圖解）
  * `index.md`：更新總目錄
  * `index.html`：新增卡片至「太陽系與行星科學」分類


## [2026-11-16] ingest | 太陽 (臺南市南瀛天文館)
* **原始來源**：https://taea.tn.edu.tw/astro_news/book_detail/733020a8-28ab-11eb-8a3a-12737f8ed331
* **存檔文件**：`raw/sun.md`、`raw/articles/sun.md`
* **下載資源**：`assets/images/sun_sdo_304.jpg`、`assets/images/sunspots_taea.jpg`、`assets/images/sun_size_comparison.jpg`、`assets/images/sun_layers_diagram.jpg`
* **建立/更新條目**：
  * `wiki/solar_system/sun.md`：根據真實文獻數據全面深化（元素比例 73%H/25%He、半徑分層、黑子溫度與蒙德極小期）
  * `wiki/sources/taea-sun.md`：建立第二篇文獻精讀摘要
  * `pages/sun.html`：更新獨立展示頁，整合本地實測照片與內部 SVG 向量剖面圖
  * `index.md`：更新總目錄


## [2026-11-16] ingest | 行星定義與矮行星分類 (臺南市南瀛天文館)
* **原始來源**：https://taea.tn.edu.tw/astro_news/book_detail/c20ff284-35ee-11eb-937f-a72c0803ff9e
* **存檔文件**：`raw/planet_definition.md`、`raw/articles/planet_definition.md`
* **下載資源**：`assets/images/pluto_dwarf_planets_comparison.jpg`
* **建立/更新條目**：
  * `wiki/solar_system/planet-definition-and-dwarf-planets.md`：歸類於「衛星與矮行星」，深入解析軌道清除能力與流體靜力平衡門檻
  * `wiki/sources/taea-planet-definition.md`：建立來源精讀摘要
  * `pages/planet-definition-and-dwarf-planets.html`：建立獨立展示頁（內嵌 IAU 2006 分類決策樹向量 SVG 圖解）
  * `index.md`：更新總目錄
  * `index.html`：於首頁「衛星與矮行星」次分類新增條目卡片


## [2026-11-16] style-redesign | 全面重塑為「先鋒藝術天文誌」瑞士平面設計風格
* **操作類型**：視覺系統與規範重大升級 (Avant-Garde Editorial / Swiss Graphic Design)
* **核心樣式表建立**：
  * `assets/style.css`：定義美術館紙張底色 (`#F4F3EF`)、極黑 (`#0D0D0D`)、電光鈷藍 (`#1A4BFF`)、Google Fonts (Anton, Noto Serif TC, Playfair Display, Space Mono)、外露 1px 黑色網格、超大編輯編號與幾何切角遮罩。
* **規範同步寫入**：
  * `AGENTS.md`：完整寫入先鋒藝術視覺標準，規範所有未來生成之頁面必須引用 `assets/style.css` 並遵循雜誌雙欄排版。
* **頁面全面重構與套用**：
  * `index.html`：重塑為跨頁海報式首頁、雙層分類網格、超大編輯編號 (01, 02, 03) 與即時檢索。
  * `pages/solar-system-structure.html`：重塑為雜誌雙欄排版、八角切角遮罩、瑞士對數 SVG 尺度圖與微型側邊欄。
  * `pages/sun.html` 與 `pages/planet-definition-and-dwarf-planets.html`：同步升級至統一先鋒藝術誌排版。


## [2026-11-16] style-polish | 精簡首頁文字、新增三大藝術拼貼與確立內文純淨規範
* **操作類型**：首頁視覺精化與規範正式確立
* **首頁調整 (`index.html`)**：
  * 移除 Hero 頂部多餘中繼標註與副標段落。
  * 完整移除底部黑色頁尾 (`editorial-footer`)。
  * **三大藝術拼貼**：加入右側 `OBSERVE * COSMOS` 螢光青/鈷藍層疊殘影字跡、斜切角度 `#1A4BFF` 紙質口袋露出米白相框相片、以及文章卡片「跨框重疊」超大編號 (01, 02, 03)。
* **樣式表升級 (`assets/style.css`)**：
  * 加入細膩全站美術館微顆粒質感 (`feTurbulence` 紙張雜訊)。
  * 增加拼貼元件樣式 (`.ghost-typography-stack`, `.slanted-pocket-layer`, `.pocket-peeking-photo`, `.editorial-idx-overlap`)。
* **規範手冊同步 (`AGENTS.md`)**：
  * 正式寫入第 2.4 條「首頁藝術拼貼 vs. 內頁純淨排版規範」，確立 `pages/` 嚴禁裝飾拼貼遮擋閱讀的長效準則。


## [2026-11-16] batch-ingest | 四大類地行星全收錄 (水星、金星、地球、火星)
* **原始來源**：
  * 水星: https://taea.tn.edu.tw/astro_news/book_detail/8fa25692-3608-11eb-a08c-d33c5015ac94
  * 金星: https://taea.tn.edu.tw/astro_news/book_detail/d178c3f2-4103-11eb-aef4-3a417d5ce69e
  * 地球: https://taea.tn.edu.tw/astro_news/book_detail/dc10307c-41c4-11eb-8a52-704bd17d4d1f
  * 火星: https://taea.tn.edu.tw/astro_news/book_detail/bb54077c-45c1-11eb-b879-76ccafab5a06
* **存檔文件**：
  * `raw/mercury.md`、`raw/venus.md`、`raw/earth.md`、`raw/mars.md` (同步至 `raw/articles/`)
* **下載圖片**：
  * 9 張真實天文圖檔 (`mercury_messenger.jpg`, `venus_phases_taea.jpg`, `venus_mariner10.jpg`, `earth_solar_sidereal_day.jpg`, `earth_magnetosphere.jpg`, `earth_apollo8_earthrise.jpg`, `earth_pale_blue_dot.jpg`, `mars_opposition_taea.jpg`, `mars_viking1.jpg`)
* **建立/更新結構化筆記**：
  * `wiki/solar_system/mercury.md` (04 水星)
  * `wiki/solar_system/venus.md` (05 金星)
  * `wiki/solar_system/earth.md` (06 地球)
  * `wiki/solar_system/mars.md` (07 火星)
  * 4 篇來源精讀摘要 (`wiki/sources/taea-mercury.md`, `taea-venus.md`, `taea-earth.md`, `taea-mars.md`)
* **建立獨立展示頁面 (純淨瑞士排版)**：
  * `pages/mercury.html` (DIAGRAM 04.2: 3:2 自轉公轉共振與超大金屬核 SVG)
  * `pages/venus.html` (DIAGRAM 05.3: 逆行自轉與失控溫室效應陷阱 SVG)
  * `pages/earth.html` (DIAGRAM 06.3: 太陽日 24h vs 恆星日 23h56m 幾何差 SVG)
  * `pages/mars.html` (DIAGRAM 07.3: 火星衝日線對齊與太陽風剝蝕大氣機制 SVG)
* **同步索引與首頁**：
  * `index.md`：收錄條目增至 7 篇，更新雙層分類與來源目錄。
  * `index.html`：完成「1.1 類地行星與類木行星」板塊，新增 4 張具備跨框重疊大編號 (04, 05, 06, 07) 的先鋒藝術卡片。

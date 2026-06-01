# 政府採購法極限語意圖譜與測驗系統
(Procurement Law Knowledge Graph & Quiz System)

**最後更新日期：2026-06-02**

這是一個將「政府採購法」及其相關子法、實務主題，透過自然語言處理（NLP）與 AI 輔助，轉換為立體知識圖譜（Knowledge Graph）與心智圖（Mindmap）的視覺化專案。同時內建錯題本與智能解析的題庫測驗系統。

## 核心功能

1. **🌌 極限語意圖譜 (`graph.html`)**
   - 視覺化展示母法（政府採購法）與各個子法的層級關係。
   - 利用 AI 萃取法條之間的「語意關聯（Semantic Edges）」，自動產生法規跨越、條文交集的複雜連線。
   - 支援深色/淺色模式，並可即時切換至樹狀心智圖模式。

2. **📜 法規章節心智圖 (`mindmap.html`)**
   - 將龐大的政府採購法規依照「篇、章、節、條」進行階層化的結構展示。

3. **💡 實務主題心智圖 (`thematic_mindmap.html`)**
   - 將法條與工程企管實務主題（如：招標、決標、履約管理、爭議處理）進行重組歸類，打破傳統法規排列，提供實務導向的檢索視角。

4. **🏆 測驗系統 (`index.html`)**
   - 整合政府採購法題庫，提供分類測驗功能。
   - 具備個人成績統計、AI 智能解析以及「錯題本」功能，針對弱點加強複習。

## 技術架構

- **資料處理**：Python, json, zipfile
- **圖譜運算**：D3.js (Force-directed graph)
- **心智圖**：Markmap
- **UI/UX**：Bootstrap 5, Vanilla JS (無框架)

## 如何使用

所有的主要介面皆為純前端靜態檔案（Static HTML），可直接使用瀏覽器開啟：
- 雙擊開啟 `index.html` 進入測驗系統首頁。
- 雙擊開啟 `graph.html` 進入知識圖譜視覺化介面。

---

## 檔案結構與用途說明

本專案將所有的資料處理後端腳本隱藏，只發布編譯過的前端網頁與資料集，以確保 GitHub Pages 能順利運行且檔案乾淨。

### 網頁介面 (Frontend HTML)
- **`index.html`**：政府採購法題庫測驗系統的主網頁，包含搜尋、過濾、錯題本與成績統計功能。
- **`graph.html`**：極限語意圖譜的主網頁，內建 D3.js 網狀關聯圖，並整合了心智圖的 iframe 顯示框架。
- **`mindmap.html`**：法規章節架構的心智圖（由 `graph.html` 呼叫或可獨立開啟）。
- **`thematic_mindmap.html`**：實務主題歸類的心智圖（由 `graph.html` 呼叫或可獨立開啟）。

### 圖譜與題庫資料集 (JSON Datasets)
- **`legal_graph.json`**：知識圖譜的核心節點檔案，包含政府採購法母法及所有子法的條文內容。
- **`all_practices_analyzed.json`**：經過 AI 智能解析的題庫資料庫，包含題目、選項、正確解答、解析與關聯法條。
- **`bundled_nodes.json`**：用於圖譜中，將同屬於一個母法或子法的條文節點進行群組化（Bundle）的結構資料。
- **`semantic_edges.json`**：記錄「法規層級」跨法規的語意交集連線資料（由 AI 萃取）。
- **`semantic_article_edges.json`**：記錄「條文層級」跨條文的精確語意交集連線資料（由 AI 萃取）。
- **`thematic_groups.json`**：實務主題歸類的規則檔，定義了招標、決標、履約等實務分類底下的關聯法條。
- **`all_laws_text.json`**：政府採購法相關法規的原始純文字彙整檔（供索引使用）。
- **`law_keys.json`**：法規全名與簡稱的對照表，用於關鍵字搜尋與關聯比對。

### 心智圖匯出檔 (OPML)
- **`legal_mindmap.opml`**：官方體系的法規章節心智圖，可下載並匯入至 XMind、MindNode 等心智圖軟體編輯。
- **`thematic_mindmap.opml`**：實務主題心智圖的匯出檔。

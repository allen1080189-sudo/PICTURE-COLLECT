# AGENTS.md - Q版人物梗圖庫 (Git-Driven Folder & Meme System)

本文件旨在規範本專案之靜態架構、主題資料夾管理規範與內容發布流程。本專案採 Git 規範驅動開發（類似課堂範例「呆一布講義」），透過維護程式碼內建之資料庫，讓 GitHub Pages 上的所有訪客皆能瀏覽最新成果。

---

## 1. 系統架構與發布模式
- **發布模式**：Git-Driven Static Web App（部署於 GitHub Pages）。
- **常駐內容保證**：所有對外公開的主題資料夾與梗圖圖片，皆儲存於 `index.html` 內之 `initialData` 物件。
- **即時編輯與匯出**：網頁提供右上角「匯出公開資料」功能，可將訪客或開發者在瀏覽器端新增的內容轉換為 JSON，方便回貼至 `initialData` 並發布至 GitHub。

---

## 2. 資料模型 (Data Schema)

### (1) 資料夾模型 (Folder Schema)
```json
{
  "id": "folder-work",
  "name": "菲比",
  "description": "菲比啾比梗圖",
  "coverImage": "圖片 Data URL (Base64) 或 SVG"
}

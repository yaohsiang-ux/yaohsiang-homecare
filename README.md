# 燿翔居家長照機構 官網

單一 `index.html` + `assets/`（logo、favicon），純靜態、無後端、無框架。

**✅ 已上線（2026-07-06）**：https://yaohsiang-ux.github.io/yaohsiang-homecare/
Repo：https://github.com/yaohsiang-ux/yaohsiang-homecare（GitHub Pages，main 分支根目錄）

改版流程：改本資料夾的 `index.html` → `git add -A && git commit -m "..." && git push` → 約 1 分鐘後自動更新。

## 本機預覽
```bash
cd "$(dirname "$0")" && python3 -m http.server 8788
# 瀏覽 http://localhost:8788
```

## 上線方式（擇一）
1. **Netlify Drop**（最快）：開 https://app.netlify.com/drop ，把整個 `官網/` 資料夾拖進去即得網址，可再綁自訂網域。
2. **GitHub Pages**：建 repo → 上傳這兩個檔案 → Settings → Pages → 選 main branch。
3. **Cloudflare Pages**：同上，支援自訂網域 + 免費 SSL。

## 上線後待辦
- `index.html` head 內有一段註解（og:url / og:image / canonical），把 `https://example.com/` 換成正式網域後解除註解——LINE/FB 分享才會出圖。
- 若申請自訂網域，建議 `yaohsiang.tw` 或 `yaohsianghomecare.com` 之類。

## 活動集錦（欄位已建置，內容後補）

1. 照片放入 `assets/gallery/`（建議先壓到寬 1200px 以下、去識別化／確認肖像權）。
2. 編輯 `assets/gallery/list.json`：
```json
{ "items": [ { "src": "assets/gallery/檔名.jpg", "caption": "活動說明", "date": "2026/07" } ] }
```
3. push 後首頁「活動集錦」區塊自動出現（list 為空時整區隱藏）。

## 衛教專欄（欄位已建置，供文章管線對接）

1. 用 `articles/_template.html` 產生文章頁：替換 `{{TITLE}}`、`{{DATE}}`、`{{SUMMARY}}`、`{{CONTENT}}`（內文用 `<h2>/<p>/<ul>` 即可），存成 `articles/<slug>.html`。
2. 在 `articles/list.json` 加一筆（新文章放最前面，首頁顯示前 6 篇）：
```json
{ "articles": [ { "slug": "檔名不含副檔名", "title": "文章標題", "date": "2026/07/06", "summary": "一兩句摘要" } ] }
```
3. push 後首頁「衛教專欄」區塊自動出現。第二階段可讓每日衛教文章管線直接寫這兩類檔案。

## 內容來源
- 機構簡介：01_行政管理/單位營運備份/.../fb/專業/單位簡介：.docx
- 立案資訊：01_行政管理/許可證照/設立許可證書_109年.png（北市社老字第10930548741號）
- Logo：~/Desktop/yaohsiang/logo.jpg（已壓縮至 assets/）
- 品牌色：暖橘 #D65A31、琥珀金 #E6AF2E、深棕 #4B3621（文字層級用 #B8431C 以符合 WCAG AA 對比）

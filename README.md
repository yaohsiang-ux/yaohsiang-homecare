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

## 內容來源
- 機構簡介：01_行政管理/單位營運備份/.../fb/專業/單位簡介：.docx
- 立案資訊：01_行政管理/許可證照/設立許可證書_109年.png（北市社老字第10930548741號）
- Logo：~/Desktop/yaohsiang/logo.jpg（已壓縮至 assets/）
- 品牌色：暖橘 #D65A31、琥珀金 #E6AF2E、深棕 #4B3621（文字層級用 #B8431C 以符合 WCAG AA 對比）

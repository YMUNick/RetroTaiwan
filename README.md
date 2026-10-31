# 吾名小站 MyName Station — 2005 懷舊網誌模擬器

一個純前端的單頁小玩具，帶你回到 2005 年：在 IE6 的外框裡寫網誌、從別人家複製 CSS 語法貼進後台、改到整個版跑掉、再把網址丟給朋友看。

**不需要任何後端。** 全部是靜態檔案，直接放上 GitHub Pages 就能跑：

- `index.html`：吾名小站首頁（熱門相簿、留聲機、新聞焦點、PK 擂台、大頭寶製造機、會員區）
- `blog.html`：網誌模擬器（寫網誌、改版型、分享網址）

## 功能

- **經典網誌 DOM 結構**：`#container` / `#banner` / `#pageheader` / `.description` / `#content` / `.blogbody` `.datediv` `.title` `.innertext` `.posted` / `#links` `.sidetitle` `.side` / `#footer`，可以照當年的方式手寫 CSS 蓋過去
- **5 種基本版型**：吾名原味藍、粉紅公主、黑色系視覺、草莓牛奶、經典灰視窗，另外附一份「語法大全」可以一鍵加入
- **點陣字體**：預覽區優先用 `PMingLiU / 新細明體`，12px、行高 1.5，並關掉字體反鋸齒
- **側欄**：個人資料大頭貼（沒放圖就自動產生像素頭像）、誰來我家、人氣計數器、復古音樂盒、最新留言
- **復古音樂盒**：用 Web Audio 即時合成的 8-bit 原創小曲（不用任何音檔），也可以貼自己的 mp3 網址
- **網誌小工具**：顏文字、轉成火星文、粉紅字 / 跑馬燈 / 閃亮字、滑鼠星星尾巴、禁止右鍵
- **自動存檔**：存在 `localStorage`
- **網址分享**：用 `lz-string` 把整個小站壓縮進 `#data=...`，朋友打開就是唯讀的參觀模式，也可以把這個版型帶回自己的後台
- **存成 PNG**：用 `html-to-image` 把預覽區拍成截圖

## 部署到 GitHub Pages

1. 把 `index.html` push 到 repo 的 `main` 分支
2. 到 **Settings → Pages**，Source 選 `Deploy from a branch`，Branch 選 `main` / `(root)`
3. 等一兩分鐘，打開 `https://<帳號>.github.io/<repo>/`

## 本機預覽

```bash
python -m http.server 8765
```

然後打開 http://localhost:8765/

## 安全性

文章可以寫 HTML（當年就是這樣玩的），但輸出前會拿掉 `<script>`、`<iframe>`、`on*` 事件屬性和 `javascript:` 連結，所以點開別人的分享網址也不會跑對方塞進來的程式。

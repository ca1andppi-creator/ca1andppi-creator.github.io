# Ahrefs Site Explorer 測試網站

這個目錄可以直接發佈到 GitHub Pages 的使用者首頁：

```text
https://你的GitHub帳號.github.io/
```

## 1. 在 GitHub 建立 repository

登入 GitHub，建立一個 **Public** repository，名稱必須是：

```text
你的GitHub帳號.github.io
```

例如 GitHub 帳號是 `alice`，repository 名稱就是：

```text
alice.github.io
```

不要勾選先建立 README，讓 repository 保持空白。

## 2. 初始化並推送

在此目錄開啟 PowerShell：

```powershell
git init -b main
git config user.name "你的名字"
git config user.email "你的GitHub驗證Email"
git add .
git commit -m "Create Ahrefs test site"
git remote add origin https://github.com/你的GitHub帳號/你的GitHub帳號.github.io.git
git push -u origin main
```

GitHub 若要求登入，使用瀏覽器登入或 Personal Access Token；不要把 token 寫進 repository。

推送完成後等 1–2 分鐘，打開：

```text
https://你的GitHub帳號.github.io/
```

看到測試頁面就代表網站已公開。

## 3. 在 Ahrefs 驗證

1. 在 Ahrefs 選擇 `Add website` / `Verify website`。
2. 輸入：

   ```text
   https://你的GitHub帳號.github.io/
   ```

3. 選擇 HTML 檔案驗證。
4. Ahrefs 會提供一個類似 `ahrefs_xxxxxxxx.html` 的檔案。
5. 把該檔案下載到這個 repository 根目錄，和 `index.html` 放在同一層。
6. 提交及推送：

   ```powershell
   git add ahrefs_*.html
   git commit -m "Add Ahrefs verification file"
   git push
   ```

7. 確認以下網址能直接開啟驗證檔內容：

   ```text
   https://你的GitHub帳號.github.io/ahrefs_xxxxxxxx.html
   ```

8. 回到 Ahrefs 按 `Verify`。

驗證成功後即可使用已經開放給 Verified website 的 Site Explorer。新網站可能只會顯示很少或零筆自然搜尋資料，這是正常的；這個網站主要用來熟悉介面。

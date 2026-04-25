## 部署到 Cloudflare Worker

1. 準備 wrangler.jsonc
    ``` jsonc
    {
        "name": "blog",
        "compatibility_date": "2026-03-30",  // Update to today's date
        "assets": {
            "directory": "./dist"
            // "not_found_handling": "404-page" // If you have a custom `src/pages/404.astro` page
        }
    }
    ```
    - name: 要與 Cloudflare 上設的 Worker 的 name 相同
    - assets.directory: 靜態網頁檔案路徑
    - compatibility_date: 最後更新日期
2. 執行 `pnpm dlx wrangler deploy`


## Junction 連結 `src/content/posts`

``` cmd
mklink /J ".\src\content\posts" "<實際目錄路徑>"
```

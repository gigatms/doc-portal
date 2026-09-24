# doc.gigatms.com.tw Document Portal Draft v4

這是 GIGA-TMS 文件入口網站的規畫草案，沿用 `security.gigatms.com.tw` 的暗色資安站同系列視覺，並依內部會議結論調整為 `doc.gigatms.com.tw` 的兩階段文件架構。

## Two-phase document architecture

### Phase 1 — RED-DA Doc

第一階段先完成 RED-DA Doc 公開入口、單一 A–Z 型號索引、型號文件 metadata、簽署核准後的 PDF 下載與不可變更的歷史版本 archive。產品家族（例如 RFID、125 kHz 與 GP series）保留在每筆文件 metadata，不再於 `/doc/red-da/` 下分成不同目錄或區塊。

目前頁面中的型號、版本、日期、文件編號與 PDF 連結仍是 planning placeholder，不代表任何已核准公開的正式文件。

### Phase 2 — CRA Doc

第二階段才導入 CRA Doc，並以 **2027/12/11** 作為 CRA 文件公開公布的規畫節點。CRA 在 Phase 1 不列為可下載文件；目前已保留獨立規畫頁 `/doc/cra/`，並預留 RFID、125 kHz 與 GP Series 等未來產品擴充區。待相關評估、產品家族文件與公開核准完成後，再逐步加入正式頁面與 PDF 下載連結。

## Directory structure

```text
doc.gigatms.com.tw/
├── index.html                              # 兩階段文件入口首頁
├── CNAME                                   # 未來 GitHub Pages 網域設定範例
├── assets/
│   ├── style.css                           # 暗色首頁共用樣式
│   ├── doc.css                             # 文件目錄與 archive 樣式
│   ├── advisory.css                         # 產品安全更新公告頁樣式
│   └── GIGA-TMS_wordmark_color_transparent.png
├── doc/
    ├── red-da/
    │   ├── index.html                      # Phase 1 RED-DA Doc 目錄
    │   └── archive/
    │       └── index.html                  # Phase 1 RED-DA 歷史文件 archive
    └── cra/
        └── index.html                      # Phase 2 CRA Doc 規畫與預留頁
└── security-advisories/
    └── index.html                           # 產品安全更新公告頁
```

## URL rules

Current model alias:

```text
/doc/red-da/<model>.pdf
```

Immutable historical version:

```text
/doc/red-da/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

所有型號在 HTML 目錄中依 A–Z 排列；產品家族僅作為 metadata，不直接作為主要 PDF URL 的必要路徑段，以避免分類變更時破壞既有產品 URL。

## Public / internal boundary

公開入口只放已簽署、已核准公開的 RED-DA Doc 或未來 CRA Doc。技術檔案、SBOM、資安風險評估、威脅模型、測試報告、漏洞資料與 OEM 機密文件維持在內部受控系統，不放入 `doc.gigatms.com.tw`。

## Status

This is a static planning draft. No GitHub repository, DNS configuration, production deployment or official DoC PDF publication was performed. Before publication, confirm the original company-approved SVG/AI/EPS wordmark, final product list, PDF approval workflow, CNAME/DNS, canonical URLs, sitemap, robots policy and reviewer ownership.

## Official links

- Company website: <https://www.gigatms.com.tw>
- Security reporting: <https://security.gigatms.com.tw>
- Future document portal: <https://doc.gigatms.com.tw>
- Product security updates: `/security-advisories/`
- Security reporting: <https://security.gigatms.com.tw>

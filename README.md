# doc.gigatms.com.tw Document Portal Draft v4

這是 GIGA-TMS 文件入口網站的規畫草案，沿用 `security.gigatms.com.tw` 的暗色資安站同系列視覺，並依內部會議結論調整為 `doc.gigatms.com.tw` 的兩階段文件架構。

## Two-phase document architecture

### Phase 1 — RED-DA Doc

第一階段先完成 RED-DA Doc 公開入口、單一 A–Z 型號索引、型號文件 metadata、簽署核准後的 PDF 下載與不可變更的歷史版本 archive。產品家族（例如 RFID、125 kHz 與 GP series）保留在每筆文件 metadata，不再於 `/doc/red-da/` 下分成不同目錄或區塊。

ER750A series 是目前第一份待審核的 RED-DA 文件候選項目。其 PDF、A–Z 索引項目與 SHA-256 checksum 已放入獨立發布分支，必須完成工程與文件管制審核並合併 Pull Request 後，才會成為公開文件。其餘型號仍為 planning placeholder。

### Phase 2 — CRA Doc

第二階段才導入 CRA Doc，並以 **2027/12/11** 作為 CRA 文件公開公布的規畫節點。CRA 在 Phase 1 不列為可下載文件；目前已保留獨立規畫頁 `/doc/cra/`，未來與 RED-DA 一樣採單一 A–Z 型號索引，不依 RFID、125 kHz 或 GP Series 分成產品家族頁面。產品家族資訊只保留在每筆文件 metadata 中，待相關評估與公開核准完成後，再逐步加入正式 PDF 下載連結。

## Directory structure

```text
doc.gigatms.com.tw/
├── index.html                              # 兩階段文件入口首頁
├── CNAME                                   # 未來 GitHub Pages 網域設定範例
├── assets/
│   ├── style.css                           # 暗色首頁共用樣式
│   ├── doc.css                             # 文件目錄與 archive 樣式
│   ├── advisory.css                         # 產品安全公告頁樣式
│   └── GIGA-TMS_wordmark_color_transparent.png
├── doc/
    ├── red-da/
    │   ├── index.html                      # Phase 1 RED-DA Doc 目錄
    │   ├── ER750A.pdf                       # 首份 RED-DA 候選文件（審核中）
    │   └── archive/
    │       └── index.html                  # Phase 1 RED-DA 歷史文件 archive
    └── cra/
        └── index.html                      # Phase 2 CRA Doc 規畫與預留頁
├── robots.txt                                # 預覽期間禁止搜尋引擎索引
└── security-advisories/
    └── index.html                           # 產品安全公告（Advisories）頁
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

CRA model alias:

```text
/doc/cra/<model>.pdf
```

CRA immutable historical version:

```text
/doc/cra/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

## Public / internal boundary

公開入口只放已簽署、已核准公開的 RED-DA Doc 或未來 CRA Doc。技術檔案、SBOM、資安風險評估、威脅模型、測試報告、漏洞資料與 OEM 機密文件維持在內部受控系統，不放入 `doc.gigatms.com.tw`。

## Status

The GitHub Pages site is now published from `main`. The revised ER750A RED-DA DoC was merged through Pull Request #1 and is available at `/doc/red-da/ER750A.pdf`. The public portal remains limited to signed and approved documents; internal technical evidence, SBOMs, risk assessments and OEM-confidential material remain outside this repository.

The custom domain `doc.gigatms.com.tw` is configured in GitHub Pages, but its DNS record must resolve before the custom URL can be reached. The GitHub Pages fallback URL is `https://gigatms.github.io/doc-portal/` while DNS propagation is pending.

## Official links

- Company website: <https://www.gigatms.com.tw>
- Security reporting: <https://security.gigatms.com.tw>
- Official document portal: <https://doc.gigatms.com.tw>
- Product security advisories: `/security-advisories/`
- Security reporting: <https://security.gigatms.com.tw>

## Product security advisory review status

The advisory page incorporates the 2026-10-06 review direction:

- The public name is **產品安全公告 / Product Security Advisories**.
- Publication timing states that a verified vulnerability may be published when a security update or interim mitigation is available and approved, or sooner when exploitation or public disclosure requires user protection.
- Internal planning language was removed from the public empty state. The page shows the last checked date: `2026-10-06`.
- The register now reserves seven fields: Advisory ID, CVE, Product / Scope, Severity, Status, First Published and Last Updated.
- The page includes support-life and publication-boundary notes, and uses bilingual headings and descriptions.
- The official portal now permits indexing through `robots.txt` and publishes a sitemap at `/sitemap.xml`.

The integrator/OEM pre-notification paragraph remains pending the POL-001 §9 decision and is intentionally not presented as a public commitment yet.

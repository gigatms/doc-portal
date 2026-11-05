# doc.gigatms.com.tw Document Portal v2.3

GIGA-TMS 公開文件入口網站，提供已簽署、已核准公開的 EU DoC 文件查詢與下載，依型號列出適用法規。自 2027/12/11 起，適用 CRA 的產品其 CRA 符合性將依 Article 28(3) 併入該型號單一 EU DoC，不另設獨立聲明目錄。

## Two-phase document architecture

### Phase 1 — EU DoC

第一階段提供 EU DoC 公開入口、單一 A–Z 型號索引、型號文件 metadata、簽署核准後的 PDF 下載與不可變更的歷史版本 archive。產品家族（例如 RFID、125 kHz 與 GP series）保留在每筆文件 metadata，不在 `/doc/eu-doc-red/` 下分成不同目錄或區塊。

目前公開型號及其適用法規以正式 [EU DoC A–Z 型號索引](https://doc.gigatms.com.tw/doc/eu-doc-red/) 為準；索引逐型號列示適用法規，PDF 下載網址維持既有固定路徑。

`PCR300A` 與 `PCR300F` 共同對應同一份 EU DoC PDF，網站保留兩筆型號索引以方便查詢，但不重複存放文件。

對於同一份 DoC 涵蓋多個型號，網站同時提供每個型號的相容主文件路徑，並由各型號路徑指向同一份合併 PDF。例如 `MF7.pdf` 與 `MR2.pdf` 均指向 `MF7_MR2.pdf`；`PCR300A.pdf` 與 `PCR300F.pdf` 均指向 `PCR300A_PCR300F.pdf`。此設計可支援業務以單一型號組成下載網址，不需知道合併檔名。

### Phase 2 — CRA requirements in the EU DoC

自 **2027/12/11** 起，適用 CRA 的產品，其 CRA 符合性將依 Article 28(3) 併入該型號單一 EU DoC；不另設獨立的 CRA 符合性聲明目錄。既有 `/doc/cra/` 資訊頁及預留路徑保留不變。

CRA Article 14 通報義務自 **2026/9/11** 起已適用；產品安全通報請參閱 <https://security.gigatms.com.tw>。 CRA Article 14 reporting obligations apply from **11 September 2026**; product security reports should be submitted through <https://security.gigatms.com.tw>.

## Directory structure

```text
doc.gigatms.com.tw/
├── index.html                              # 公開文件入口首頁 v2.3
├── CNAME                                   # GitHub Pages 自訂網域
├── assets/
│   ├── style.css                           # 首頁共用樣式
│   ├── doc.css                             # 文件目錄與 archive 樣式
│   ├── advisory.css                        # 產品安全公告頁樣式
│   └── GIGA-TMS_wordmark_color_transparent.png
├── doc/
│   ├── eu-doc-red/
│   │   ├── index.html                      # Phase 1 EU DoC A–Z 目錄
│   │   ├── <model-or-family>.pdf             # 已核准公開之 EU DoC PDF
│   │   └── archive/
│   │       └── index.html                  # EU DoC 歷史文件 archive
│   └── cra/
│       └── index.html                      # CRA 整合說明頁（保留既有資訊路徑）
└── security-advisories/
    └── index.html                          # 產品安全公告頁
```

## URL rules

Current EU DoC model PDF path（已公開固定路徑）：

```text
/doc/eu-doc-red/<model>.pdf
```

Immutable historical version（歷史版本路徑）：

```text
/doc/eu-doc-red/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

所有型號在 HTML 目錄中依 A–Z 排列；產品家族僅作為 metadata，不直接作為主要 PDF URL 的必要路徑段，以避免分類變更時破壞既有產品 URL。主文件 URL 與歷史版本 URL 一旦對外公布即不可變更、不可重用，也不可改指向其他 PDF；若內容更新，必須建立新的版本 URL 並保留原 URL。

All model records are sorted in A–Z order. Product family is metadata rather than a required PDF URL path segment. Once a current or historical URL is published, it is immutable: do not replace, reuse or retarget it. Issue a new version URL for any update and retain the original URL.

保留的 CRA 資訊頁路徑（不是獨立聲明下載分類）：

```text
/doc/cra/
```

由於適用 CRA 符合性將併入相應型號的單一 EU DoC，不建立或發布獨立的 CRA 型號 PDF／archive 目錄；保留現有 `/doc/cra/` 說明頁路徑。

## Public route and legacy compatibility

EU DoC 的公開顯示名稱改為中性名稱；下列已公開路徑、PDF 檔名及 archive 路徑均維持不變：

```text
/doc/eu-doc-red/
/doc/eu-doc-red/<model>.pdf
/doc/eu-doc-red/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

The `/doc/eu-doc-red/` route is the unchanged public route for the neutral catalogue name **EU DoC**. The former `/doc/red-da/` catalogue page remains a compatibility redirect, and existing PDF paths under `/doc/red-da/<model>.pdf` remain available so previously published links continue to work.

## Public / internal boundary

公開入口只放已簽署、已核准公開的 EU DoC。適用的 CRA 符合性將自 2027/12/11 起併入該型號 EU DoC。技術檔案、SBOM、資安風險評估、威脅模型、測試報告、漏洞資料與 OEM 機密文件維持在內部受控系統，不放入 `doc.gigatms.com.tw`。

## Status

The GitHub Pages site is published from `main` at [https://doc.gigatms.com.tw](https://doc.gigatms.com.tw). The public portal is limited to signed and approved documents. Internal technical evidence, SBOMs, risk assessments and OEM-confidential material remain outside this repository.

The current public release is **Document Portal v2.3**. The custom domain is configured with HTTPS enforcement.

## Official links

- Company website: <https://www.gigatms.com.tw>
- Security reporting: <https://security.gigatms.com.tw>
- Official document portal: <https://doc.gigatms.com.tw>
- Product security advisories: `/security-advisories/`

## Product security advisory page

The advisory page uses the public name **產品安全公告 / Product Security Advisories** and includes:

- Advisory ID, CVE, Product / Scope, Severity, Status, First Published and Last Updated fields.
- Support-life and publication-boundary notes.
- Bilingual headings and descriptions.
- Direct links to the GIGA-TMS security reporting site and document portal.

The public advisory register currently has no published entries.

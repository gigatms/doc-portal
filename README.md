# doc.gigatms.com.tw Document Portal v2.1

GIGA-TMS 公開文件入口網站，提供已簽署、已核准公開的 RED-DA EU Declaration of Conformity 文件查詢與下載。網站沿用 `security.gigatms.com.tw` 的同系列視覺，並保留 Phase 2 CRA Doc 文件空間。

## Two-phase document architecture

### Phase 1 — RED-DA Doc

第一階段提供 RED-DA Doc 公開入口、單一 A–Z 型號索引、型號文件 metadata、簽署核准後的 PDF 下載與不可變更的歷史版本 archive。產品家族（例如 RFID、125 kHz 與 GP series）保留在每筆文件 metadata，不在 `/doc/red-da/` 下分成不同目錄或區塊。

目前已公開的 RED-DA 型號包括：

- ER750A
- PCR300A
- PCR300F
- PCR300M
- PCR330A
- PCR330M

`PCR300A` 與 `PCR300F` 共同對應同一份 EU DoC PDF，網站保留兩筆型號索引以方便查詢，但不重複存放文件。

### Phase 2 — CRA Doc

第二階段保留 CRA Doc 空間，公開公布節點為 **2027/12/11**。CRA 在 Phase 1 不列為可下載文件；目前保留 `/doc/cra/` 單一 A–Z 型號索引空間，不依 RFID、125 kHz 或 GP Series 分成產品家族頁面。產品家族資訊只保留在每筆文件 metadata 中，待相關評估與公開核准完成後，再逐步加入正式 PDF 下載連結。

CRA Article 14 通報義務自 **2026/9/11** 起已適用；產品安全通報請參閱 <https://security.gigatms.com.tw>。 CRA Article 14 reporting obligations apply from **11 September 2026**; product security reports should be submitted through <https://security.gigatms.com.tw>.

## Directory structure

```text
doc.gigatms.com.tw/
├── index.html                              # 公開文件入口首頁 v2.1
├── CNAME                                   # GitHub Pages 自訂網域
├── assets/
│   ├── style.css                           # 首頁共用樣式
│   ├── doc.css                             # 文件目錄與 archive 樣式
│   ├── advisory.css                        # 產品安全公告頁樣式
│   └── GIGA-TMS_wordmark_color_transparent.png
├── doc/
│   ├── red-da/
│   │   ├── index.html                      # Phase 1 RED-DA A–Z 目錄
│   │   ├── ER750A.pdf
│   │   ├── PCR300A_PCR300F.pdf
│   │   ├── PCR300M.pdf
│   │   ├── PCR330A.pdf
│   │   ├── PCR330M.pdf
│   │   └── archive/
│   │       └── index.html                  # RED-DA 歷史文件 archive
│   └── cra/
│       └── index.html                      # Phase 2 CRA Doc 型號索引空間
└── security-advisories/
    └── index.html                          # 產品安全公告頁
```

## URL rules

Current model alias（主文件路徑）：

```text
/doc/red-da/<model>.pdf
```

Immutable historical version（歷史版本路徑）：

```text
/doc/red-da/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

所有型號在 HTML 目錄中依 A–Z 排列；產品家族僅作為 metadata，不直接作為主要 PDF URL 的必要路徑段，以避免分類變更時破壞既有產品 URL。主文件 URL 與歷史版本 URL 一旦對外公布即不可變更、不可重用，也不可改指向其他 PDF；若內容更新，必須建立新的版本 URL 並保留原 URL。

All model records are sorted in A–Z order. Product family is metadata rather than a required PDF URL path segment. Once a current or historical URL is published, it is immutable: do not replace, reuse or retarget it. Issue a new version URL for any update and retain the original URL.

CRA model alias（未來主文件路徑）：

```text
/doc/cra/<model>.pdf
```

CRA immutable historical version（未來歷史版本路徑）：

```text
/doc/cra/archive/<model>-v<version>-<yyyy-mm-dd>.pdf
```

## Public / internal boundary

公開入口只放已簽署、已核准公開的 RED-DA Doc 或未來 CRA Doc。技術檔案、SBOM、資安風險評估、威脅模型、測試報告、漏洞資料與 OEM 機密文件維持在內部受控系統，不放入 `doc.gigatms.com.tw`。

## Status

The GitHub Pages site is published from `main` at [https://doc.gigatms.com.tw](https://doc.gigatms.com.tw). The public portal is limited to signed and approved documents. Internal technical evidence, SBOMs, risk assessments and OEM-confidential material remain outside this repository.

The current public release is **Document Portal v2.1**. The custom domain is configured with HTTPS enforcement.

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

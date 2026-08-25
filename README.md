# Revit MCP Research Partner

`revit-mcp-research-partner` 是一個 Codex Skill，用來協助研究與整理真實的 Revit / MCP / BIM 工作流程。它的重點不是自動產生 MCP Tool，而是把既有外掛、人工流程、Domain SOP、Issue / PR 討論、模型證據與失敗紀錄，轉換成可審查、可交接、可驗證的下一步。

這個 Skill 適合處理這類問題：

- 「我有一個既有 Revit 工作流程，想整理成 Skill 或 MCP workflow。」
- 「外掛已經能產生候選，但後面都靠人判斷，能不能沉澱成 SOP？」
- 「這個 Issue / PR / 測試紀錄到底證明到哪一層？」
- 「這個工作應該做成外掛、Domain SOP、MCP Tool proposal、GitHub Issue，還是先人工審查？」
- 「使用者自己也說不清楚問題，只知道某個 BIM 工作流程常常卡住。」

它不適合當作一般 Revit 問答、專業簽認工具、結構或法規判斷代理人，也不會把所有需求都推向 MCP Tool 化。

## 這個 Skill 解決什麼問題

許多 BIM 自動化需求一開始不是清楚的「功能需求」，而是來自現場流程：

```text
既有外掛可以做一部分
-> 人靠經驗看結果
-> 某些例外要手動處理
-> 沒有清楚證據知道完成到哪裡
-> 後續很難交接、測試或發 Issue
```

這個 Skill 的工作是先把流程拆清楚，而不是急著寫工具：

```text
理解情境
-> 檢查既有資料與流程
-> 找出候選與判斷點
-> 產生可審查的表格、SOP、Issue draft 或 SVG 脈絡圖
-> 判斷成果應該回到哪一層
-> 定義驗證方法與停止條件
```

最後的結果可能是：

- 保留既有外掛，補一份 Domain SOP。
- 做成 Skill / MCP workflow，讓 Agent 負責蒐集證據、定位例外、問少量關鍵問題。
- 發 GitHub Issue，描述缺少的介面、可重現案例與驗收條件。
- 寫 MCP Tool proposal，但只在規則清楚且確實缺少機器介面時才做。
- 停在人工作業或專業審查，不進入自動執行。

## 方法來源

這個 Skill 不是從單一模板產生，而是整合了幾個方法來源。

### 1. Codex Skill Creator 原則

Skill 本體只放會改變 Codex 決策的指引，不塞通用 BIM 教材，也不把專案演講內容原樣搬進來。長背景、案例與交付格式放在 `references/`，由 `SKILL.md` 按情境載入。

### 2. Decision-tree style questioning

這個 Skill 借用了 `grilling / grill me` 類型 Skill 的精神：不要替使用者偷做決策；先找事實，把未決問題拆成一棵決策樹。

但它不是純追問型 Skill。這裡的追問只能服務於四件事：

- 證據分類
- 既有流程轉換
- 責任與安全邊界
- 成果分流與驗證

每輪都應該盡量產出可審查 artifact，例如候選表、流程轉換表、SOP 草案、Issue draft、驗證矩陣或 SVG 圖，而不是一直問到完全清楚才開始工作。

### 3. Revit / MCP / BIM 證據分層

Skill 會明確區分不同證據層級：

| 層級 | 代表意義 | 不能混用成 |
| --- | --- | --- |
| 想法 | 假設、需求、推測 | 已完成功能 |
| 原始證據 | 文件、Issue、模型觀察、失敗紀錄 | 已驗證規則 |
| 原始碼 | 有實作或設定 | 已部署 |
| 測試通過 | 指定環境與測試通過 | 實機模型可用 |
| 建置產物 | 有產出檔案 | 已被 Revit 載入 |
| 部署 | 已安裝或發布到某處 | 實際模型結果正確 |
| 實機執行 | 指定宿主 / 模型跑過 | 已獨立驗證 |
| 讀回驗證 | 寫入後用獨立方式讀回 | 專業簽認 |
| 專業簽認 | 負責人接受指定範圍 | 可泛用到所有案例 |

### 4. `REVIT_MCP_study` Issue / PR 研究回饋

這個 Skill 是為了回饋與沉澱 [`shuotao/REVIT_MCP_study`](https://github.com/shuotao/REVIT_MCP_study) 的公開研究脈絡而整理。它參考了該專案中的 Issues、Pull Requests、維護者回覆、失敗修正與 SOP 化思路，將其中可重用的邏輯整理成研究協作方法。

目前內建的案例庫不是功能目錄，而是決策模式庫，例如：

- 候選清單不等於可以直接修改。
- Preview 不可靠時必須停止寫入。
- 被拒絕的機制也應保留替代路徑與重啟條件。
- PR、測試、截圖或 API success 不能直接當作實機部署與讀回驗證。
- 文件存在不代表 Skill 或 workflow 真的會使用它。
- 大型 PR 應拆成可獨立審查的成果。
- UI 能做到不代表公開 API 支援。
- 跨系統移植需要重新確認身份、單位、版本與能力邊界。

這個 repo 不是 `REVIT_MCP_study` 的官方組件，也不代表該專案維護者立場。它的用途是把公開互動中值得複用的研究方法整理成 Codex Skill，方便後續把案例轉成 SOP、Issue、proposal 或人工審查包。

## 安裝方式

將此資料夾放到 Codex skills 目錄：

```text
%USERPROFILE%\.codex\skills\revit-mcp-research-partner
```

重新啟動或刷新 Codex 後，Skill 會依 `SKILL.md` 的 description 被自動選用。也可以在對話中明確要求使用：

```text
使用 revit-mcp-research-partner 幫我整理這個 Revit/MCP 工作流程
```

## 使用方式

你不需要一開始就提出完整規格。可以用很模糊的方式開始：

```text
我有一套既有外掛流程，想整理成 Skill 或 MCP workflow，但不知道怎麼開始。
```

Skill 應該先做：

1. 檢查你提供的外掛文件、SOP、Issue、PR、模型證據或失敗紀錄。
2. 不重複問可以從檔案或 repo 查到的資訊。
3. 只問一到三個會改變方向的問題。
4. 先產出可審查的小成果，而不是直接提工具。

典型輸出會包含：

- 研究問題與範圍
- 已知證據與證據層級
- 工程規則、情境判斷、模型副作用與人工責任
- 建議落地方向
- 最小可行成果
- 驗證方法
- 停止條件

## 互動範例：既有流程轉換

使用者：

```text
我現在有一個 Revit 工作流程，平常是先用既有外掛跑一份清單，再靠人看結果，有些情況要手動修。我想把它整理成 Skill 或 MCP workflow，但我不知道怎麼開始。
```

Skill 應回應的方向：

```text
先不假設要做成 MCP Tool。
我要先判斷這個流程裡哪些是固定規則，哪些其實是人的判斷。

這輪只需要確認兩件事：
1. 這個流程目前最常從哪裡開始：外掛按鈕、表格、模型視圖，還是檢查報告？
2. 最常卡住的是找不到對象、判斷不一致、修改會影響模型，還是完成證據不足？
```

接著應產出流程轉換表：

| 流程段落 | 現在誰做 | 建議轉換 | 先不要做 |
| --- | --- | --- | --- |
| 外掛產生候選 | 既有外掛 | 保留為穩定前處理 | 不重寫外掛 |
| 人看候選 | 有經驗的人 | Skill 引導判斷、整理例外 | 不假裝 Agent 取代判斷 |
| 決定是否處理 | 人 | Review packet / SOP 判斷狀態 | 不直接寫入模型 |
| 後續修正 | 人或外掛 | 之後再評估 plugin / MCP Tool | 未有 preview / readback 前不執行 |

建議分流：

| 成果 | 放到哪裡 | 原因 |
| --- | --- | --- |
| 候選來源與欄位定義 | Domain SOP | 人可以照著重複檢查 |
| 例外整理與追問流程 | Skill / MCP workflow | Agent 適合協助蒐證與定位不確定性 |
| 缺少讀取候選清單的介面 | GitHub Issue 或 MCP Tool proposal | 規則清楚但缺機器介面 |
| 會修改模型的步驟 | 人工審查後另案處理 | 需要 preview、rollback、readback、人工核准 |

## 互動範例：Issue / PR 證據審查

使用者：

```text
這個 PR 測試都過了，可以說功能完成了嗎？
```

Skill 應回應的方向：

```text
測試通過只代表它通過那組測試，不等於已部署、已在 Revit 跑過、或已在指定模型讀回驗證。
我會把目前證據拆成：程式碼、測試、建置、部署、實機執行、讀回驗證、專業確認。
```

輸出範例：

| Claim | Current evidence | Status | Next check |
| --- | --- | --- | --- |
| 程式碼存在 | 指定 PR revision | confirmed | 檢查 handler / call path |
| 測試通過 | CI 或本機測試紀錄 | test-level only | 不宣稱部署 |
| Revit 實機可用 | 無指定模型與讀回紀錄 | not proven | 需要授權 dry run 與獨立 readback |

## 互動範例：API 能力研究

使用者：

```text
Revit 畫面上可以做這個設定，那 API 應該也可以吧？
```

Skill 應回應的方向：

```text
不能用畫面能力推測 API 能力。
需要先確認 Revit 版本與官方 Revit API 文件，再判斷是否有公開、支援、可測試的介面。
```

若官方資料未確認，狀態應標為：

```text
officially_unverified
```

並停止在研究或 Issue proposal，不應直接進入實作。

## 產出物

Skill 會依情境產出不同 artifact：

| 需求 | 主要產出 |
| --- | --- |
| 不知道下一步 | Action register |
| 想重複交接流程 | Domain SOP draft |
| 判斷是否需要機器介面 | MCP Tool proposal |
| 準備回報 repo | GitHub Issue draft |
| 需要人決定 | Review packet |
| 關係與流程複雜 | SVG context / workflow diagram |
| 多個假設要驗證 | Validation matrix |

內建 SVG assets：

- `assets/research-routing-map.svg`
- `assets/research-navigation-map.svg`
- `assets/issue-pr-evidence-workflow.svg`

這些圖是審查表面，不是工程證據本身。

## 專案結構

```text
SKILL.md
agents/
  openai.yaml
references/
  research-output-contract.md
  revit-mcp-boundaries.md
  routing-targets.md
  practical-deliverables.md
  case-based-work-modes.md
  case-evidence-patterns.md
  research-navigation.md
  research-case-library.md
  response-examples.md
assets/
  research-routing-map.svg
  research-navigation-map.svg
  issue-pr-evidence-workflow.svg
```

## 邊界與限制

- 不替代工程判斷、結構簽認、法規責任或模型修改責任。
- 不預設所有工作都應 MCP Tool 化。
- 不宣稱 Agent 比熟練 Revit 使用者更快，除非有可比 benchmark。
- 不把 Issue 回覆、commit、測試通過、截圖或 API success 當成讀回驗證或正式部署。
- 未取得明確同意，不修改 SC REVIT、Revit MCP、BIM Agent、公司內部資料或 live model。
- 涉及模型 mutation 時，必須先有 preview、rollback / Undo、independent readback 與人工核准。
- 涉及專業軟體 API 功能研究或實作時，必須查官方資料，不以 Agent 記憶或推測作為依據。

## 目前狀態

這是研究加強版基準。它已包含：

- Skill entrypoint
- Codex metadata
- 9 份 reference
- 3 份 SVG workflow assets
- 從 `REVIT_MCP_study` 公開 Issues / PRs 萃取的案例邏輯

已做基本結構檢查與安全掃描。`quick_validate.py` 需要本機 Python 環境有 `PyYAML`；若環境缺少 PyYAML，需使用手動 frontmatter、reference link、placeholder、mojibake 與敏感字串掃描替代。

## License

No license has been selected for this repository yet. Do not assume reuse rights beyond the repository owner's stated terms.

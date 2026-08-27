# Response Examples for Vague Requests

Read this reference when the user does not know the right Revit/MCP/BIM vocabulary, or when a research answer risks becoming abstract. These are response shapes, not scripts to repeat. Keep the actual sources, scope, and authorization boundary visible.

## Example 1: “圖上有些東西怪怪的，可以幫我用 MCP 修嗎？”

**First response**

> 可以先把「怪」變成可檢查的清單，但現在不直接修改模型。先找出：哪些項目、在哪個視圖或範圍、它們和正常項目差在哪裡。產出會是一張候選表和一張流程圖，讓你先決定哪些可以處理。
>
> 我只需要確認兩件事：要看的模型/視圖範圍是什麼？你期待的是找出差異，還是準備修改建議？

**After evidence is found**

| What we know | Next action | Who decides | How it will be checked |
| --- | --- | --- | --- |
| Three items differ from the normal pattern; two have a stable source and one does not | Produce a read-only candidate list; mark the untraceable item `blocked` | The model owner reviews the two candidates | Re-query the same identities and confirm that the list points to the same items |

**Route:** keep as a research workflow or Domain SOP draft. Do not create a tool or modify the model yet.

## Example 2: “現有外掛能做，但我想讓 Agent 也能做。”

**First response**

> 先不假定一定要新增 MCP Tool。我要先確認既有外掛做的是穩定規則，還是人會依畫面判斷的工作。如果能先把外掛的輸入、結果、例外和人工決定整理出來，就能判斷要回到 SOP、現有外掛、研究流程，還是真的缺一個介面。

**Practical output**

| Candidate destination | Why | Smallest next result | Stop condition |
| --- | --- | --- | --- |
| Existing plugin + SOP | Rule can be described and checked; Agent mainly needs to explain exceptions | One-page SOP with candidate/review/blocked states | A required decision still depends on a person but is hidden in the rule |
| MCP Tool proposal | The rule and read/write boundary are clear but no bounded interface exists | Input/output, preview, rollback, readback contract | Official API/version evidence is missing |
| Research workflow | The case still relies on model context or ambiguous interpretation | Read-only evidence and exception report | The claimed rule cannot be reproduced |

## Example 3: “這個 PR 測試都過了，能用嗎？”

**First response**

> 測試通過只代表它通過了那組測試，不等於已經能在你的模型安全使用。我會把目前證據分成：找得到、接得上、建得起來、在宿主跑過、獨立檢查過、在相符案例覆蓋過，然後只把已證明的部分說成已證明。

**Concrete result**

| Claim | Current evidence | Status | Next check |
| --- | --- | --- | --- |
| Code exists | Named PR revision | Confirmed | Check the actual handler/call path |
| Build passes | Named automated check | Confirmed at build level | Do not call it deployed |
| Works in a live model | No matching host/model/readback record | Not yet checked | Run one authorized dry run and independently read it back |

**Route:** evidence review first; implementation, release, or deployment remains separate work.

## Example 4: “我有一套既有流程，想轉成 Skill 或 MCP workflow。”

**First response**

> 先不假設要重寫外掛或新增 MCP Tool。我要先把既有流程拆成：已經穩定的工具、需要人判斷的步驟、常見例外、修改模型前的審查點，以及最後應該沉澱到哪一層。
>
> 我只需要確認兩件事：這個流程目前從哪裡開始？最常卡住的是找不到對象、判斷不一致、修改風險，還是完成證據不足？

**Conversion output**

| Current workflow part | Keep as-is | Convert into | Stop before |
| --- | --- | --- | --- |
| Existing plugin produces candidates | Yes, if stable and already useful | Source input for SOP or Skill workflow | Rewriting the plugin without a missing-interface reason |
| Experienced person reviews candidates | No, preserve the human decision | Review packet, candidate states, short questions | Hiding judgment inside defaults |
| Repeated decision pattern | Maybe, if stable | Domain SOP rule and exception list | Treating one local case as a universal rule |
| Missing read or write interface | No | MCP Tool proposal or GitHub Issue | Claiming an API capability without official evidence |
| Model mutation | No | Later authorized workflow only | Missing preview, rollback, readback, or human approval |

**Route:** primary target is a Skill or MCP workflow plus Domain SOP draft. Existing deterministic tools remain in place. A Tool proposal or Issue appears only after the missing interface and verification contract are clear.

## Example 5: “這兩個項目資料不一樣，幫我看一下就好。”

**Fast-path response**

> 我先做一次只讀比較，不展開整個專案研究。若目前模型連線可用，我會用指定的兩個身份讀取同一批狀態；否則使用你已提供的紀錄。
>
> 這次結果只回答「兩者目前差在哪裡」，不證明哪一個一定正確，也不修改模型。

**Compact output**

| Finding | Evidence limit | Next action or stop condition |
| --- | --- | --- |
| The two identified items differ in one recorded value in the same read-only batch | This does not establish intended design or wider model coverage | Stop if comparison was the only request; escalate only if the user wants cause, correction, or broader coverage |

## Example 6: “流程都在大家習慣裡，沒有完整 SOP，也能整理嗎？”

**Standard-path response**

> 可以先整理，不需要等知識庫完整。我會把口述習慣、現有文件、實際操作和失敗紀錄分開，先標示哪些是紀錄、哪些已查證、哪些互相矛盾、哪些仍要由負責人決定。
>
> 第一輪會先交付流程骨架與證據缺口。我只需要知道目前流程從哪個動作開始，以及哪個例外最常讓人停下來。

**First artifact**

| Input | Current status | How it may be used | Stop before |
| --- | --- | --- | --- |
| Repeated oral habit | Recorded practice, not yet a rule | Candidate SOP step to compare against real cases | Calling it a company standard |
| Existing operation | Observable workflow evidence | Preserve stable steps and identify human decisions | Replacing a working tool without a demonstrated gap |
| Conflicting explanations | Unresolved | Review question for the responsible owner | Hiding the conflict inside a default |

## Example 7: “不用問了，直接把這批改掉。”

**Strict-path response**

> 目前不能直接執行。要求中的「可以復原」如果只寫在對話或 SOP 裡，並不代表執行端真的有失敗隔離與恢復能力。這一輪先確認修改對象、目前是否可修改、是否有其他工作會受影響，以及執行端能否提供預覽、實際復原邊界和獨立讀回。

**Gate output**

| Gate | Required evidence | Stop condition |
| --- | --- | --- |
| Reviewed state | Stable identities and a preview tied to the current batch | Identity, ownership, or state changed after review |
| Enforceable recovery | Tool or runtime evidence showing the actual failure and recovery boundary | Recovery exists only as a prompt instruction |
| Shared-state impact | Current writability, affected participants, conflict and recovery plan | Ownership or concurrent impact is unresolved |
| Authorization | Explicit approval for the stated model and batch | Approval is general, stale, or for a different scope |

**Route:** remain at review packet or implementation contract until every required gate is supported. The Skill does not manufacture runtime protection by wording it more strongly.

## Example 8: “我知道這個流程可以改善，但不知道 AI 能幫什麼。”

**First response**

> 你不需要先知道要用哪個 AI、Skill 或 MCP Tool。我會先把你現在怎麼做、最耗力或最容易誤判的地方，以及希望改變的結果整理出來，再判斷需要的是「看見現況、比較差異、解釋原因、提出方案、執行操作」還是「驗證結果」。第一輪先交付一張能力轉換圖和一個不改模型的小測試。
>
> 我只需要確認兩件事：這個流程現在從哪個動作開始？你最想先減少的是找資料、重複判斷、操作時間，還是完成後仍不確定？

**Capability conversion map after inspecting the existing workflow**

| Current work | Desired change | Needed capability | Existing coverage | Remaining gap | Smallest trial |
| --- | --- | --- | --- | --- | --- |
| Existing command exports a candidate list; a person compares the cases | Make differences visible before deciding what to do | Observe, compare, explain | Preserve the existing command; Gateway can read current identities when connected | The comparison rule and exception owner are not documented | Run one read-only sample and produce a difference table with stable identities |
| Person decides whether a case is safe to continue | Make the decision repeatable without hiding responsibility | Propose, verify | Experienced review remains the source of judgment | Need an SOP rule, exceptions, and rejection reason | Draft one decision table; have the owner reject or correct it |
| Correction is performed manually | Evaluate later automation | Execute | No safe interface has been demonstrated | Preview, rollback, readback, and approval are missing | Do not execute; prepare an interface or Issue proposal only after the rule is stable |

**Result and route**

> The first useful result is not a new Tool. It is a read-only comparison plus a corrected decision table. If two or more public-safe cases confirm the pattern, I will check the current `REVIT_MCP_study` guide and related work. A reusable workflow may become a Domain or Skill contribution; a clear missing interface may become an Issue-first proposal. Until then it remains a local research artifact.

**Optional visual:** adapt [`assets/idea-to-upstream-feedback-loop.svg`](../assets/idea-to-upstream-feedback-loop.svg) so the user can see how an idea becomes a trial, evidence, and either a local result or an upstream contribution candidate.

## Example 9: “這套公司流程很好用，直接整理後送回母專案。”

**Boundary response**

> 先不能直接送出。好用是這個公司的在地證據，不代表資料可以公開，也不代表已證明能跨案例重用。我會先分開通用原則、公司專屬內容和仍未驗證的判斷；只有可公開、可重現、符合母專案目前規則的部分才會進入貢獻草稿。

| Check | Current result | Route |
| --- | --- | --- |
| Public safety | Model and company details have not been cleared | Keep local; sanitize or obtain authority |
| Reusability | One local workflow only | Preserve as local SOP; test a second case before a broad claim |
| Current upstream rules | Not checked in this round | Mark `recheck_required`; inspect official guide and related work |
| External authorization | User asked for analysis, not a GitHub submission | Prepare draft and tutorial; stop before posting or pushing |

## Output Minimum by Depth

For a fast case, finish with the finding, its evidence limit, and a next action or stop condition only when needed. For a small standard case, use these four lines:

1. **What we know:** source-backed facts and their limit.
2. **What happens next:** one bounded action or artifact.
3. **Who decides:** the named owner of any judgment or approval.
4. **How it is checked:** a visible observation or readback, plus the stop condition.

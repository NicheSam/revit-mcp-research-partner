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

## Output Minimum for a Small Case

Even for a short conversation, finish with these four lines:

1. **What we know:** source-backed facts and their limit.
2. **What happens next:** one bounded action or artifact.
3. **Who decides:** the named owner of any judgment or approval.
4. **How it is checked:** a visible observation or readback, plus the stop condition.

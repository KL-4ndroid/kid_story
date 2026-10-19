# Automation Roadmap v0.1

## 核心原則

先自動化「已經證明有效的流程」，不要先把未知流程寫成大型系統。

因此分成 4 層。

---

## Level 0｜Founder Beta：只在 ChatGPT 內跑

目的：驗證體驗。

使用者只要輸入：

> 開始 Kid Story Founder Beta v0.1

ChatGPT 依 `prompts/ORCHESTRATOR.md` 依序完成：

1. Expectation Setup
2. Intake
3. Safety Gate
4. Child Profile
5. Story Goal
6. Story Plan
7. Draft
8. QA
9. Illustration Bible
10. Page Plan
11. Parent Note
12. Feedback

此階段不追求付款、寄信、網站自動化。

### 人工只保留

- 最終 Safety 判斷
- 最終故事 QA
- 是否交付

---

## Level 1｜標準化服務：ChatGPT + GitHub 規格庫

目的：可以開始服務 5–10 組封閉測試家庭。

GitHub 保存：
- Prompt 版本
- 規格
- QA checklist
- 匿名化 bug／friction
- changelog

每位家長的真實資料只存在服務對話／交付流程，不放公共 repo。

每次生成都標記：

```text
story_engine_version: 0.1
questionnaire_version: 0.1
safety_version: 0.1
qa_version: 0.1
```

如此之後才知道「哪個版本比較好」。

---

## Level 2｜半自動商品化

目的：創辦人每本只需要做最後 QA。

理想流程：

```text
家長進入體驗
→ 對話式 Intake
→ 自動結構化
→ Safety Gate
→ Story Plan
→ Story Draft
→ 自動 QA
→ 生成頁面規格
→ 創辦人 Review Queue
→ Approve / Revise
→ 交付
→ 自動詢問 48h / 7d feedback
```

### Founder Dashboard 最小需要看

- Case ID
- 主題
- Safety 狀態
- QA 分數
- 需要人工注意的原因
- 是否已核准
- 修改次數
- 回饋狀態

---

## Level 3｜真正對外自動化

只有在 20–50 個案例驗證後才做。

完整商業流程還會需要：
- 顧客入口
- 金流
- 個資同意
- 儲存
- 交付
- 客服／退款

如果堅持「內容生產只由 ChatGPT 完成」，仍然可行；但**付款、身份同意、檔案交付等商業基礎設施不應假裝能只靠一段對話完全取代**。

因此本專案把「AI 生產系統」與「商業基礎設施」分開設計。

---

# ChatGPT Orchestrator 自動化邏輯

每個 case 內部維護以下狀態：

```json
{
  "case_id": "KS-YYYYMMDD-001",
  "mode": "founder_beta",
  "state": "INTAKE",
  "versions": {
    "questionnaire": "0.1",
    "story_engine": "0.1",
    "safety": "0.1",
    "qa": "0.1"
  },
  "safety": {
    "status": "pending",
    "reason": null
  },
  "story": {
    "goal": null,
    "qa_score": null,
    "approved": false
  }
}
```

狀態只能依 `docs/FLOW.md` 移動，避免模型跳步。

# 自動 QA

在故事草稿後，自動做第二次獨立審查：

1. 找說教句
2. 找羞辱／恐嚇
3. 找成人化心理語言
4. 找不合理的完美結局
5. 找未授權家庭細節
6. 找年齡不適配語言
7. 找 AI 套句

若任一 Critical Fail，必須重寫後才可顯示給家長。

# Human-in-the-loop 規則

以下 case 一律不可全自動交付：

- Safety = REVIEW
- QA < 13/16
- 修改超過 1 次仍未通過
- 家長指出重大誤解
- 涉及敏感家庭情境

# Feedback Loop

每次 beta 回饋都轉成其中一類：

- BUG：流程錯誤
- CONTENT：故事品質
- SAFETY：安全／界線
- UX：問答體驗
- VALUE：付費價值
- VISUAL：插畫／排版

每週只整理「重複出現」與 P0/P1 問題，避免被單一意見帶著跑。

# 自動化真正的成功指標

不是「完全不用人」。

而是：

> 同樣品質下，創辦人每本只需要處理模型真的需要人判斷的 10–20%。

第一階段目標：30–45 分鐘／本。
成熟後目標：10–20 分鐘／本。

# Kid Story — 孩子專屬睡前故事書

> 不是「用 AI 隨機寫童話」，而是把爸媽不知道怎麼說的事情，變成孩子願意聽完的一個故事。

## 專案目標

建立一套可以高度標準化、低人力運作的個人化兒童故事產品。第一階段聚焦 3–6 歲孩子的一般生活適應情境，例如：不想睡覺、怕黑、第一次上學、不想刷牙、家中有弟弟妹妹、容易生氣。

本 repo 是產品的 **Single Source of Truth**，保存：

- 產品定位與商業規格
- 家長問答流程
- Story Engine
- 兒童安全與內容界線
- 故事 QA 規則
- 插畫／角色一致性規格
- 創辦人測試流程
- 使用者回饋與版本迭代紀錄
- 未來自動化規格

## v0.1 的核心原則

1. **先驗證體驗，再寫大量程式。**
2. 一次只處理一個日常小難題。
3. 不把產品定位成醫療、心理治療或行為矯正。
4. 不羞辱、不恐嚇、不用「乖／不乖」作為故事核心。
5. 孩子是故事中的主動角色，不是被大人改造的對象。
6. 故事結尾允許問題仍然存在，只要孩子多了一點理解或願意嘗試。
7. AI 產出一定要經過 QA gate 才能交付。
8. **不得把真實兒童個資、照片、姓名、家庭細節或家長問卷答案提交到這個公開 repo。** Repo 只保存模板、規格、匿名統計與虛構範例。

## MVP 流程

```text
家長開始
  ↓
商品與界線說明
  ↓
家長問答 Intake
  ↓
安全篩選 Safety Gate
  ↓
孩子人物卡 Child Profile
  ↓
故事目標 Story Goal
  ↓
故事骨架 Story Plan
  ↓
完整故事 Draft
  ↓
Story QA + Safety QA
  ↓
插畫規格 Illustration Bible
  ↓
頁面配置 Page Plan
  ↓
家長共讀頁 Parent Note
  ↓
交付
  ↓
48 小時 / 7 天回饋
  ↓
版本迭代
```

## 目前里程碑

- [x] 建立 repo
- [x] 定義 v0.1 產品方向
- [ ] 完成產品 PRD
- [ ] 完成 Intake 問答
- [ ] 完成 Story Engine v0.1
- [ ] 完成 Safety Gate v0.1
- [ ] 完成 Founder Beta 腳本
- [ ] 創辦人本人完成第一次體驗
- [ ] 收集第一次使用回饋
- [ ] Story Engine v0.2
- [ ] 產出第一本完整 prototype
- [ ] 對外封閉測試 5–10 組家庭

## 專案資料夾

```text
docs/
  PRODUCT.md              # 產品與商業規格
  FLOW.md                 # 完整服務流程與狀態機
  QUESTIONNAIRE.md        # 家長問答流程
  STORY_ENGINE.md         # 故事生成規則
  SAFETY.md               # 安全界線與拒絕／轉介規則
  QA.md                   # 故事品質檢查
  FOUNDER_BETA.md         # 創辦人第一輪體驗
  AUTOMATION.md           # 自動化藍圖
prompts/
  ORCHESTRATOR.md         # ChatGPT 主控提示規格
schemas/
  intake.schema.json      # Intake 結構化資料格式
  feedback.schema.json    # 回饋資料格式
```

## 第一階段成功標準

不是先追求「完全自動化」，而是證明：

- 孩子願意聽完故事
- 家長覺得「這真的像我家孩子」
- 故事沒有說教感或廉價 AI 感
- 生成流程可重複
- 創辦人每本人工檢查可控制在合理範圍
- 5–10 組封閉測試後，有明確付費意願

當這些成立，再把已驗證流程逐步自動化。

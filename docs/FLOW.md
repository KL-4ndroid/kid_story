# End-to-End Flow v0.1

## 狀態機

```text
START
 ↓
EXPECTATION_SETUP
 ↓
INTAKE
 ↓
SAFETY_GATE
 ├─ PASS → CHILD_PROFILE
 ├─ NEEDS_CLARIFICATION → INTAKE
 └─ OUT_OF_SCOPE → STOP_WITH_GUIDANCE
 ↓
STORY_GOAL
 ↓
STORY_PLAN
 ↓
DRAFT
 ↓
QA
 ├─ FAIL → REVISION
 └─ PASS → ILLUSTRATION_BIBLE
 ↓
PAGE_PLAN
 ↓
PARENT_NOTE
 ↓
DELIVERY_PREVIEW
 ↓
PARENT_APPROVAL
 ├─ SMALL_REVISION → REVISION
 └─ APPROVED → FINAL_DELIVERY
 ↓
FEEDBACK_48H
 ↓
FEEDBACK_7D
 ↓
LEARNING_LOG
```

## 各階段職責

### 1. EXPECTATION_SETUP
先讓家長知道：
- 這是親子共讀故事，不是治療
- 一次只選一個生活情境
- 不保證孩子行為立刻改變
- 可以使用暱稱，不必提供真名
- 不需要提供孩子照片即可完成

### 2. INTAKE
採聊天式問答，不一次丟 20 題表單。
目標 6–10 分鐘完成。

必要欄位：
- 孩子稱呼／暱稱
- 年齡
- 主題
- 真實情境描述
- 孩子的主觀反應
- 喜歡的事物
- 熟悉的人／玩偶／環境
- 家長希望孩子得到的感受
- 禁忌元素

### 3. SAFETY_GATE
先分類再寫故事。

PASS：一般生活適應。
OUT_OF_SCOPE：危機、自傷、虐待、嚴重暴力、明顯需要醫療／心理專業評估之情況。

不得用故事取代專業協助。

### 4. CHILD_PROFILE
整理成一張內部人物卡，不直接照抄家長文字。
包含：
- 年齡語言層級
- 主角特徵
- 喜好
- 熟悉物件
- 核心感受
- 故事中可使用的個人化元素

### 5. STORY_GOAL
只能有一個主要目標。
格式：

> 希望孩子在故事結束後，不一定「改變行為」，但可以多理解 ______，並願意嘗試 ______。

### 6. STORY_PLAN
先產生 6–8 個 beat，不直接寫全文。
若骨架不自然，在此修正最省成本。

### 7. DRAFT
依 Story Engine 寫全文。

### 8. QA
至少檢查：
- 是否像孩子本人
- 是否說教
- 是否羞辱／恐嚇
- 是否把大人答案塞進孩子嘴裡
- 語言是否符合年齡
- 是否有可讀的故事性
- 是否自然收尾
- 是否有過度承諾

### 9. ILLUSTRATION_BIBLE
建立角色一致性設定：
- 髮型／髮色
- 膚色描述
- 睡衣／服裝
- 喜歡的顏色
- 陪伴角色
- 固定道具
- 禁止變動元素

### 10. PAGE_PLAN
把故事拆為 14–18 頁，每頁標註：
- 文字
- 畫面重點
- 角色表情
- 構圖
- 是否需要跨頁

### 11. PARENT_NOTE
一頁即可。
包含：
- 今晚可以怎麼讀
- 可以問的一個開放問題
- 不建議的追問方式
- 明天可嘗試的一個小行動

### 12. DELIVERY_PREVIEW
先讓家長預覽故事文字與封面方向，再做最終版本，降低返工。

### 13. FEEDBACK
48 小時：體驗反應。
7 天：重讀、家長實際使用感、是否願意付費／推薦。

## v0.1 人工與自動化分工

ChatGPT 可負責：
- 問答
- 資料結構化
- Safety 初篩
- Story Goal
- 大綱
- 故事
- QA 初檢
- 插畫規格
- 頁面規劃
- 家長共讀頁
- 回饋整理

創辦人保留：
- Safety 最終判斷
- 故事最終 QA
- 是否交付
- 回饋後版本調整

目標不是一開始 100% 無人，而是先做到 80–90% 可重複，再逐步移除人工瓶頸。
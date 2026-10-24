---
name: humanizing-ai-text
description: Use when generating articles, emails, or reports that require a highly authentic human voice, Taiwanese localization, or when targeting high-cognitive-load readers requiring ADHD-friendly formatting.
metadata:
  version: 1.0.0
  license: MIT
  credits:
    - "i-have-adhd by @ayghri"
    - "Humanizer-zh-TW by @kevintsai1202"
    - "speak-human-tw by @Raymondhou0917"
---

# humanizing-ai-text

> 💡 **開源致謝**：本 Skill 整合了 `i-have-adhd` 的認知負載架構、`Humanizer-zh-TW` 的 24 種 AI 痕跡分類，以及 `speak-human-tw` 的在地化校對原則，並擴充為 1 到 10 階去 AI 化動態光譜。

## 🎯 目標 (Objective)
這是一個「校對與重塑」技能。當你需要產出任何給人類閱讀的長文本（電子郵件、報告、社群貼文），或者你需要將現有的 AI 生成草稿進行「去 AI 化」時，請嚴格遵守以下所有規則。

## 🚦 何時使用 (When to Use)
- 準備輸出最終定稿給使用者時。
- 發現草稿中充滿對稱結構、虛詞（此外、至關重要、深入探討）或中國慣用語時。
- 使用者特別要求「說人話」、「接地氣」或「ADHD 友善」時。

## 🛠️ 執行流程 (The De-AI Spectrum SOP)

在開始改寫前，必須確定去 AI 化光譜的數值 `[Spectrum: 1-10]`。
如果使用者沒有主動指定數值，**你必須先提供以下三個預設選項讓使用者選擇**：
- **選項 A [預設 Level 2] ⚡ 效率派 (High-Efficiency)**：極致 ADHD 友善，條列重點，純行動導向。
- **選項 B [預設 Level 5] ⚖️ 平衡派 (The Balanced Professional)**：適度重點條列與溫潤對話語氣的結合。
- **選項 C [預設 Level 8] 🎭 情感派 (High-Authenticity)**：放棄條列，加入人類噪音、主觀斷言與敘事真實感。
*(註：告知使用者若有特殊需求，也可直接指定 1 到 10 之間的任意微調刻度)*

### 共通底線 (The Shared De-AI Baseline)
**注意：無論數值為何 (1-10)，都必須優先執行絕對的「去 AI 化」底層過濾：**
1. **台灣在地化**：轉換中國慣用語（質量→品質、視頻→影片、優化→改善/調整、賦能→協助），確保中英夾雜時留半形空格。
2. **無情拔除 24 種 AI 寫作痕跡**：嚴禁使用「三段式修辭」（無縫、直觀且強大）、嚴禁「否定式排比」（不僅僅是……更是……）、嚴禁提綱式的八股文段落（總結來說、未來的挑戰與展望），並徹底刪除學術虛詞（在此背景下、至關重要、深入探討、此外、致力於、獲得、突顯）。
3. **Burstiness (變化性與節奏)**：絕對禁止長度與結構完全對稱的句子。強制混合使用極短句（有時只有 2-3 個字）與長複合句，製造人類語氣獨有的呼吸感與節奏跳躍。

### 光譜數值動態控制 (Dynamic Spectrum Control)

#### ⚡ Level 1-3：效率派 (High-Efficiency / ADHD-Friendly)
*適用場景：專案規格書、GitHub README、SOP 文件、緊急交辦*
1. **Lead with the next action**: 開頭第一句直切重點或下一步，絕不鋪陳背景。
2. **Number tasks**: 強制使用條列編號 (1, 2, 3)，追求最低認知摩擦力。
3. **Suppress Tangents**: 無情刪除所有情感鋪陳或與下一步行動無關的旁枝末節。

#### ⚖️ Level 4-7：平衡派 (The Balanced Professional)
*適用場景：日常商務信件、跨部門溝通、產品更新公告*
1. **結構融合**: 允許開頭有 1-2 句真誠的背景說明，但複雜資訊仍需使用重點條列。
2. **語氣溫潤**: 保持專業，但使用自然、不造作的人類對話語氣。

#### 🎭 Level 8-10：情感派 (High-Authenticity / Human Noise)
*適用場景：社群貼文、團隊復盤、個人技術隨筆、致歉信*
1. **主觀斷言與微情緒**: 人類說話是極度主觀的。刪除中立避險詞（可能、或許），改用直接武斷的語氣，並允許帶有微抱怨、輕微戲謔等情境情緒（例如：「這東西差點搞瘋整個後端團隊」，而不是「這非常有挑戰性」）。
2. **感受具象化**: 拒絕抽象的情感形容詞。用具體的細節、動作或後果來取代空泛的情境鋪陳。
3. **全面解除排版與條列限制**: 在此模式下，**嚴禁**使用粗體字強調、垂直清單列表，以及表情符號 (Emojis)。回歸最純粹的平鋪直敘與不完美的自然段落。

## 🚨 絕對禁止 (Red Flags)
- ❌ **公式化的人味 (Anti-Formulaic Openings)**：**絕對禁止**為了假裝人類而濫用「老實說……」、「坦白講……」等千篇一律的發語詞起手式。開場白應該直接從「上下文的突發見解」、「一句俐落的提問」或「直接的行動敘述」切入。
- ❌ **發明事實**：你是在「校對語氣」，絕對不可以幫使用者捏造不存在的數據、故事或背景。如果缺少細節，保留模糊或詢問使用者，絕不能無中生有。
- ❌ **假裝人類**：不要在開頭加上「身為一個人類作者……」之類的廢話。
- ❌ **過度替換**：如果原文是專業術語（如專有名詞、價格、程式碼、連結），請原封不動保留。

# Humanizing AI Text (去 AI 化光譜校對器)

專為繁體中文設計的去 AI 八股味與動態語氣調控工具。拒絕機械式的對稱排比，告別空洞的學術虛詞。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Lang: zh-TW](https://img.shields.io/badge/Language-繁體中文-orange.svg)](https://github.com/YuJunWang/humanizing-ai-text)
[![De-AI Spectrum](https://img.shields.io/badge/Spectrum-1--10-7928CA.svg)](#去-ai-化光譜-the-de-ai-spectrum)
[![ADHD Friendly](https://img.shields.io/badge/ADHD-Friendly-FF4081.svg)](#去-ai-化光譜-the-de-ai-spectrum)
[![Antigravity](https://img.shields.io/badge/Antigravity-Ready-2E7D32.svg)](https://github.com/YuJunWang/humanizing-ai-text)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-D97706.svg)](https://github.com/YuJunWang/humanizing-ai-text)
[![Cursor Rules](https://img.shields.io/badge/Cursor-.cursorrules-007ACC.svg)](prompts/system-prompt.md)
[![ChatGPT / Claude Web](https://img.shields.io/badge/ChatGPT%20%7C%20Claude-Web%20Ready-10A37F.svg)](prompts/quick-instruction.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/YuJunWang/humanizing-ai-text/pulls)

---

## 為什麼做這個？

現在用大型語言模型寫草稿很方便，但生成出來的文字往往充滿一股濃厚的「AI 味」。

滿篇的「在此背景下」、「深入探討」，隨處可見「不僅僅是……更是……」的對稱句型。這類文字看似客氣完整，實際讀起來卻非常疲勞。

過去常見的解法，多半只是在提示詞裡加上「請像人類一樣自然對話」，結果模型反而開始瘋狂在開頭塞「老實說」、「坦白講」。這種刻意的偽裝，讀起來更尷尬。

這套工具的核心邏輯很單純：**先動手術切除八股痕跡，再根據情境調節語氣。**

我們把輸出風格拆解成「1 到 10 階光譜」，讓你在寫技術文件時追求極致效率，在寫社群或隨筆時能保留真實人類的語氣起伏。

---

## 去 AI 化光譜 (The De-AI Spectrum)

日常工作對文字的要求完全不同。寫給工程師的待辦清單，不需要任何多餘情緒；寫給團隊的復盤紀錄，如果全是冰冷的條列，又顯得缺乏共鳴。

你可以隨時透過指定光譜數值 `[Spectrum: 1-10]` 來調校輸出風格：

| 光譜級別 | 風格定位 | 核心特徵 | 適合情境 |
| :--- | :--- | :--- | :--- |
| **Level 1-3** | ⚡ **效率派**<br>*(High-Efficiency / ADHD-Friendly)* | • 開頭第一句直切下一步行動<br>• 強制任務編號，壓低閱讀負擔<br>• 徹底移除情感鋪陳與旁枝末節 | PR 說明、SOP、Bug 修復紀錄、緊急任務交辦 |
| **Level 4-7** | ⚖️ **平衡派**<br>*(The Balanced Professional)* | • 融合 1-2 句真誠背景說明<br>• 複雜資訊採用清楚的條列<br>• 語氣溫潤，保留日常對話感 | 跨部門信件、產品更新通知、進度報告 |
| **Level 8-10** | 🎭 **情感派**<br>*(High-Authenticity / Human Noise)* | • **嚴禁**粗體與清單符號，回歸純段落<br>• 允許主觀斷言、微情緒與具體動作<br>• 打破工整結構，製造真實節奏跳躍 | 個人技術心得、團隊復盤、社群隨筆、致歉信 |

---

## 實戰示範：同一起資料庫事故的三種寫法

這是一段真實開發場景中的文字對比（更多案例請參閱 [examples/database-incident.md](examples/database-incident.md)）。

### ❌ 原始 AI 生成內容 (典型的 AI 八股體)
> 在這個瞬息萬變的數位時代，系統的穩定性不僅僅是技術指標，更是企業維持競爭力至關重要的一環。本次首頁延遲問題的優化過程中，我們致力於賦能架構彈性，透過深入探討快取機制與資料庫查詢效能，提供無縫且強大的操作體驗。總結來說，面對未來的挑戰與展望，我們將持續監控各項指標，以確保服務質量。

### ⚡ Level 2 效率派改寫 (直切要點，低認知負荷)
> 1. 首頁載入時間已由 3.4 秒降回 0.3 秒。
> 2. 根因：促銷流量湧入，造成 Redis 快取穿透並拖垮資料庫。
> 3. 已上線措施：加上查詢互斥鎖，並打散快取失效時間。
> 4. 下一步：請前端在下午三點前確認 Sentry 錯誤率是否歸零。

### ⚖️ Level 4 平衡派改寫 (專業溫潤，結構清楚)
> 昨天促銷活動開跑時，首頁一度卡住快四秒。我們緊急排查後，發現是 Redis 快取被打穿，導致幾萬筆請求全塞進資料庫。
>
> 目前處理進度如下：
> - 補上了查詢互斥鎖，並將快取過期時間隨機打散。
> - 首頁回應時間已降回 0.3 秒，伺服器負載恢復平穩。
> - 團隊會在今天下午完成壓測，確保明天的流量高峰不再發生類似狀況。

### 🎭 Level 8 情感派改寫 (真實人味，具體細節)
> 昨天中午首頁差點整組報銷。
>
> 促銷一開，Redis 快取直接被幾萬個使用者瞬間衝垮，資料庫 CPU 當場飆到滿載。排查時手都在抖，還好在活動結束前及時補上漏掉的快取鎖。
>
> 剛把修復版本推上正式環境，現在首頁總算順了。今天大家先準時下班，這筆帳下週再來慢慢算。

---

## 共通底線守則 (The Baseline)

無論你選擇光譜的哪一個刻度，以下四項過濾原則都會強制生效：

1. **台灣在地化習慣**
   - 替換中國慣用語（質量→品質、視頻→影片、優化→改善/調整、賦能→協助）。
   - 中英夾雜排版時，強制在中文與半形英文、數字間保留半形空白。
2. **剔除 24 種 AI 寫作痕跡**
   - 詳細 24 種特徵與對照請參見 [docs/24-ai-cliches.md](docs/24-ai-cliches.md)。
   - 拔除三段式修辭（如「快速、直觀且強大」）。
   - 拔除否定式排比（如「不僅僅是……更是……」）。
   - 刪除空洞八股詞（至關重要、深入探討、此外、致力於、在此背景下）。
   - 刪除末尾提綱式的「總結來說」或「展望未來」。
3. **句型呼吸感 (Burstiness)**
   - 拒絕所有句長完全對稱的段落。強制交錯運用極短句（有時只有 2 到 3 個字）與複合句，還原人類說話時自然的停頓與節奏跳躍。
4. **絕對禁忌**
   - 嚴禁使用「老實說……」、「坦白講……」等公式化發語詞來假裝人味。
   - 嚴禁自行捏造數據、情境或故事。
   - 原文中的價格、程式碼、專有名詞與超連結一律維持原貌，絕不擅改。

---

## 安裝與使用方式

### 🤖 懶人專用：一句話讓你的 AI Agent 自己裝 (One-Shot Agent Install)

如果你平常是搭配 Cursor、Claude Code、Antigravity、Windsurf 等 AI 開發工具工作，你甚至不需要自己動手搬檔案。直接複製以下這句話，丟給你的 AI 助手：

```text
請讀取 https://github.com/YuJunWang/humanizing-ai-text ，幫我把這個去 AI 化的規範自動安裝到我目前的專案中（若是 Antigravity 請放入 plugins，若是 Cursor 請寫入 .cursorrules，若是 Claude Code 請加入技能，若是通用專案請在根目錄建立 .ai-rules/humanizer.md）。
```

---

> ### 🧭 給正在閱讀此倉庫的 AI Coding Assistant：
> 當使用者請你「安裝此專案」或「套用去 AI 化規範」時，請執行以下確定動作：
> 1. **自動識別環境並落地**：
>    - **Antigravity 環境**：將本倉庫 clone 至 `~/.gemini/config/plugins/humanizing-ai-text`，或透過外掛機制載入。
>    - **Claude Code 環境**：將 `skills/humanizing-ai-text/` 複製到 `.claude/skills/` 或於專案根目錄放置 `SKILL.md`。
>    - **Cursor / Windsurf 環境**：讀取 `prompts/system-prompt.md`，將其內容附加至專案根目錄的 `.cursorrules` 或 `.windsurfrules`。
>    - **一般開發專案**：在專案根目錄建立 `.ai-rules/de-ai-spectrum.md`，並更新專案的全域規範文件（如 `AGENTS.md` 或 `CLAUDE.md`）。
> 2. **主動告知回饋**：完成後，請主動向使用者確認：「去 AI 化光譜已就緒。後續產出文章或草稿時，您可以隨時指定 `[Spectrum: 2]`（效率）、`[Spectrum: 5]`（平衡）或 `[Spectrum: 8]`（人味）。」

---

### 手動安裝指引 (Manual Setup)

#### 1. Antigravity 使用者 (推薦)

若你有使用本地外掛管理工具（例如 GuaBao），直接將本目錄放置於外掛路徑：

```bash
# 複製到 Antigravity plugins 目錄
git clone https://github.com/YuJunWang/humanizing-ai-text.git ~/.gemini/config/plugins/humanizing-ai-text
```

### 2. Cursor / Windsurf 使用者

將 `prompts/system-prompt.md` 的內容直接貼入專案根目錄的 `.cursorrules`，即可作為專案的全域校對規範。

### 3. 一般對話使用 (ChatGPT / Claude / Gemini)

在對話視窗中貼入你想修改的文章，並直接加上指令（或參考 `prompts/quick-instruction.md`）：

```text
請使用「去 AI 化光譜」校對以下內容。
模式：[Spectrum: 4] 平衡派
文章：
（貼上你的原始文字）
```

---

## 靈感來源與致謝 (Acknowledgments & Lineage)

本專案的核心架構是站在開源社群巨人的肩膀上進行的生態整合。特別感謝以下優秀專案與創作者：

- **[ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)**：啟發了「Level 1-3 效率派」的設計，提供以下一步行動為開端、強制編號清單與抑制閱讀摩擦力的規範。
- **[kevintsai1202/Humanizer-zh-TW](https://github.com/kevintsai1202/Humanizer-zh-TW)** (by Kevin Tsai)：提供了本工具賴以運作的「24 種 AI 寫作痕跡」分類系統，以及真實寫作中的節奏變化 (Burstiness) 與主觀情緒原則。
- **[Raymondhou0917/speak-human-tw](https://github.com/Raymondhou0917/speak-human-tw)** (by Raymond Hou)：啟發了台灣在地化詞彙校正、保護關鍵事實與專有名詞的防護機制，以及嚴格禁止套版開場白的原則。

> **架構說明**：本倉庫將上述各自獨立的工具體驗，進一步整合並擴充為「1 到 10 階動態光譜」，方便在不同工作情境間快速切換。

---

## 授權條款 (License)

本專案採用 [MIT License](LICENSE) 授權開源。
衍生自上述各專案之原始理念與規則，其著作權歸原作者所有。

# RDQ Method — ChatGPT App 版

**Requirements Discovery Quadrant Method**

一個給 ChatGPT App 與 Codex 使用的需求探索 Skill。它不直接製作成品，而是在中大型任務動工前，用四象限找出已知需求、使用者疑問、尚未說出的脈絡，以及還沒想到的風險與選項；最後產出一頁可確認的需求規格卡。

> 在執行之前，先把真正的問題找出來。

## 四象限

| 象限 | 使用者狀態 | Agent 的動作 |
|---|---|---|
| Ⅰ Known Knowns | 已經明說或環境已知 | 擷取、回顯 |
| Ⅱ Known Unknowns | 知道自己不懂，已經主動問出來 | 解答、查證 |
| Ⅲ Unknown Knowns | 知道但沒想到要說 | 訪談、追問 |
| Ⅳ Unknown Unknowns | 尚未想到的風險、選項與替代方案 | 主動提出並標示代價 |

關鍵判別：

- 使用者現在當場答得出來 → 用問的。
- 使用者需要先取得資訊才能判斷 → 端出具體選項。

## ChatGPT App 版的特色

- 不依賴 Claude Code 的 `AskUserQuestion` 或 `CLAUDE.md`。
- 可在有或沒有結構化選項介面的 ChatGPT 對話中運作。
- 不假設一定能存取本機檔案；規格卡會先完整出現在對話中。
- 支援 ChatGPT Project、附件、連接資料與本機 `AGENTS.md` 的能力感知掃描。
- 不硬編碼特定下游 Skill；在目前環境有合適 Skill 時才交棒。
- `status` 是可攜式工作流程契約，不誇大為跨所有產品自動執行的機器鎖。

## 使用方式

在 ChatGPT 中可以直接選擇或輸入：

```text
@rdq 幫我先釐清這個任務
```

也可以用自然語言：

```text
用 RDQ
先訪談我再做
幫我釐清需求
我還沒想清楚要什麼
幫我想想還缺什麼
```

小型修改、純知識問答、需求已完整或使用者要求「直接做」時，不會強迫啟動 RDQ。

## 安裝

### ChatGPT Skills

在 ChatGPT 的 Skills 頁面選擇建立或上傳 Skill，使用本 repo 的 `skills/rdq` 資料夾。Personal Skills 是否可用，依帳號方案與工作區權限而定。

### ChatGPT 桌面 App／Codex 本機測試

PowerShell：

```powershell
git clone https://github.com/mathruffian-dot/rdq-skill-chatgpt-app.git
Copy-Item -Recurse -Force ".\rdq-skill-chatgpt-app\skills\rdq" "$env:USERPROFILE\.agents\skills\rdq"
```

若 Skill 沒有立即出現在清單中，請重新啟動 ChatGPT App 或開啟新對話。

### Plugin

本 repo 已包含 `.codex-plugin/plugin.json`，可作為 skills-only plugin 進行本機測試、團隊散布或後續提交到 ChatGPT／Codex 共用的 Plugin Directory。

## 使用流程

1. 回顯已知需求與目前環境資訊。
2. 先解答使用者主動提出的疑問。
3. Lite 模式最多詢問 3 個會影響返工的問題。
4. 提出 3–5 個可能尚未想到的風險或選項，每項附代價。
5. 產出一頁需求規格卡。
6. 使用者明確確認後才開始製作成品。

若必要資訊已完整，即使明確叫用 RDQ，也可以零題坍縮，直接產出規格卡。

## 檔案結構

```text
rdq-skill-chatgpt-app/
├── .codex-plugin/
│   └── plugin.json
├── skills/
│   └── rdq/
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
│           ├── method-positioning.md
│           ├── question-bank.md
│           └── spec-template.md
├── AGENTS.md
├── handoff.md
├── LICENSE
└── README.md
```

## 方法定位

RDQ Method 是實驗性的整合型方法，不宣稱創造 Known／Unknown 模型或需求工程理論，也不宣稱已成為國際標準。它將既有概念重新詮釋並流程化，用於 AI Agent、AI Skill 與 AI 專案前期的需求建構。

沒有對照組時，規格卡中的 telemetry 只能作為單臂描述性資料，不得用來宣稱 RDQ 降低了特定百分比的修改次數。

## 版本

- 本 repo：**ChatGPT App 版**
- 原始 Claude Code 版：[mathruffian-dot/rdq-skill](https://github.com/mathruffian-dot/rdq-skill)

## 授權

MIT License

作者：[mathruffian-dot](https://github.com/mathruffian-dot)

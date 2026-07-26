# RDQ Method — ChatGPT App 版（專案藍圖）

> 任何 Agent 接手時先讀本檔與 `handoff.md`。

## 專案簡介

將 RDQ Method 需求探索四象限法改寫為 ChatGPT App 與 Codex 可共同使用、可公開散布的 Agent Skill／skills-only Plugin。

## 關鍵時程

- 初版公開：2026-07-26

## 目標與路線圖

- [x] 建立 ChatGPT App 相容的 RDQ Skill。
- [x] 建立 skills-only Plugin 結構與 UI 中繼資料。
- [ ] 以實際 ChatGPT 任務持續做正向與反向觸發測試。
- [ ] 蒐集實戰修訂資料，但不做未經對照的因果宣稱。

## 專案入口

- 使用者文件：`README.md`
- Plugin manifest：`.codex-plugin/plugin.json`
- Skill 主檔：`skills/rdq/SKILL.md`
- 題庫：`skills/rdq/references/question-bank.md`
- 規格卡模板：`skills/rdq/references/spec-template.md`
- GitHub：`https://github.com/mathruffian-dot/rdq-skill-chatgpt-app`

## 固定規則

- 所有說明使用繁體中文。
- 保留象限動詞鎖定、互動預算、零題坍縮、逃生口與確認閘門。
- 不依賴 Claude Code 專屬工具或檔案。
- 不假設所有 ChatGPT 介面都有本機檔案系統或結構化多選工具。
- `status` 是工作流程契約，不宣稱能跨所有 session 自動強制執行。
- 不硬編碼私人環境才有的下游 Skill。
- Skill frontmatter 只保留 `name` 與 `description`。
- 修改後執行 Skill 與 Plugin 驗證，再提交 Git。

## 開工與收工

- 開工：先讀 `AGENTS.md`、`handoff.md`，再檢查 Git 狀態。
- 收工：更新 `handoff.md`，檢查差異後才 commit／push。
- 不把本機絕對路徑、私人筆記路徑、憑證或個資提交到公開 repo。

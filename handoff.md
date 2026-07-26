# 交接檔

## 目前做到哪

已建立 RDQ Method — ChatGPT App 版的 Skill、skills-only Plugin 結構、題庫、規格卡模板與公開 README。

## 目前狀態

初版內容、官方驗證與兩類前向測試均已完成；公開 repo 可供安裝與後續實測。

## 下一步

1. 實際從 ChatGPT Skills 上傳 `skills/rdq`，確認 UI 與 `@rdq` 叫用。
2. 持續加入不該觸發與使用者要求直接做的測試案例。
3. 收集實戰修訂資料，但不作沒有對照組的因果宣稱。

## 注意事項

- 原始 `mathruffian-dot/rdq-skill` 是 Claude Code 版，不要覆蓋。
- 本 repo 的公開署名為「RDQ Method — ChatGPT App 版」。
- telemetry 只能作為描述性資料，不可宣稱因果效果。
- 前向測試曾發現 Lite 模式問 4 題並漏掉象限Ⅳ；已強化規則，重測通過 3 題＋同輪建議。

## 最後更新

- 日期：2026-07-26
- 更新者：Codex
- Git push：已推送公開 repo

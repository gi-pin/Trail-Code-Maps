# Trail／Graft 執行環境（2026-10-22）

本機已依來源 README 安裝官方發佈套件 `@trailhq/trail-code@0.23.1`，使用 Node.js 26.4.0。這是 npm 發佈版本，不是把此 fork 重新編譯。`trail` 位於 `/opt/homebrew/bin/trail`；`~/.local/bin/graft` 連結至同套件內的 `dist/bin/graft.js`，該檔已補上執行權限，保留原技能的 graft 指令相容性。匿名 telemetry 已關閉。

Codex 已註冊全域 stdio MCP `graft`，命令為 `~/.local/bin/graft mcp`。設定依目前啟動專案的工作目錄使用圖譜；尚未建立圖譜的專案不會宣告 Graft 工具。請在實際需要分析的專案執行：

```sh
graft build '/absolute/project/path'
graft grep 'symbol' '/absolute/project/path'
```

未對吉兒／騰益整個工作區批次索引，未加入全域 hooks、讀取過往對話或啟用雲端同步。兩個工作區共用此 CLI 與 Codex MCP 設定。既有 Codex 設定已先備份至本機 `~/.codex/backups/runtime-setup-20261022/config.toml.before`，不提交到 Git。

驗證：隔離測試專案包含 `double()` 與呼叫它的 `main()`；build 得到 3 個節點、3 條邊，CLI 與 MCP `graft_find_all` 都回傳兩個正確位置。MCP 初始化與工具列舉通過。這證明本機 MCP 程序可用；目前對話尚未重新載入新 MCP 工具，需重開 Codex 工作階段再確認工具面板。

重裝指令：`DO_NOT_TRACK=1 npm install -g @trailhq/trail-code@0.23.1`。Graft 相容連結及 Codex MCP 註冊須依本機 npm 路徑重新建立，勿直接套用另一台電腦的絕對路徑。

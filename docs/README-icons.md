# 有關的檔
- src/css/common/icon.scss 狀態圖示定義處
	- item-terminal- 表示樹及 Header 狀態圖
	- list-terminal- 表示 ObjectTitles 清單狀態圖
- assets/images/*-terminal-*.svg
- src/components/Terminals/Editor/index.js 編輯頁
	- src/components/Terminals/Editor/Header.js 編輯頁頂列左邊
	- src/components/ObjectCommon/EditorTopbar.js 編輯頁首列功能表單右邊
- src/components/ObjectCommon/ObjectTitles.js 首頁 term list 

# 所有可能狀態
## 相關變數
- power = ip !== ""
- NeedToRestart
- status
	- isOff
	- isActive
	- isError
	- isBooting

Status  | Default | Disabled        | NtR            | Disabled+NtR            | Busy
:-------|:--------|:----------------|:---------------|:------------------------|:----
OFF     | off     | off-disabled    | X              | X                       | X
ACTIVE  | active  | active-disabled | active-restart | active-disabled-restart | active-busy
ERROR   | error   | error-disabled  | error-restart  | error-disabled-restart  | X
BOOTING | booting | booting-disabled| X              | X                       | booting-nolic

- src/components/Terminals/Editor/index.js
	- 它供另外兩個檔使用，已明確定義變數進去

## 函式
- terminalStatus() @ components/Tree/TreeItem.js
- getTerminalStatus() @ utils/Status.js

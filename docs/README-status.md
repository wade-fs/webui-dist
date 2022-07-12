## 狀態遷移的函式在 utils/q8c 
- 從 NOLIC -> LIC 需要 Check License & restart
- 從 LIC -> NOLIC 需要 restart
- 從 LIC -> LIC 不需要檢查 License & 不需要 restart
- 從 NOLIC -> NOLIC 不需要檢查 License & 不需要 restart

## scripts/
- terminal.sh
	- terminal 與 q8server 相同 IP(localhost), 
	- 導致無法 timeout, 因為一直 ping 得到 localhost
	- 想要實驗 timeout 的話，請用 terminal-force.sh
	- 因為實際 terminal 不可能自己說自己是 OFF, 所以無法設為 OFF
- terminal-force.sh
	- 用新的 api 強迫設定為指定的 status
	- 隨機產生 IP, 可以與 q8server 處在不同 IP, 導致會 ping 不到而 timeout

## 狀態遷移

狀態       | Lic | O | B | P | C | D | R | T | E | A
:----------|:----|:--|:--|:--|:--|:--|:--|:--|:--|:--
(O)FF      |  x  | O | o |T/o|T/o| o | x | x |T/o|T/o
(B)OOTING  |  x  | o | O | x |T/o|T/o| x | x | x | x
(P)ENDING  |  o  | o | x | O | o | o | x | x | x | x
(C)ONFIG   |  o  | o | x | x | O | o | o | o | o | o
(D)ISABLED |  o  | o | x | o | o | O | x | x | x | o
(R)EBOOT   |  o  | o | x | x | x | o | O | x | o | o
RES(T)ART  |  o  | o | x | x | x | o | x | O | o | o
(E)RROR    |  o  | o | x | x | x | o | o | o | O | x
(A)CTIVE   |  o  | o | x | x | x | o | o | o | x | O
noLicense  |  x  | o | x | x |T/o|T/o|T/o|T/o| x | x

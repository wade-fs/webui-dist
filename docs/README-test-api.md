# 已驗證

## 表格

- API: /test/ids/:tb
- 常用的表格有 term, rds, app,
- log 相關: log_terminal, log_server
- 其它: license, termovr, term_schedule, dhcp, auth, ads

### 範例

- curl http://localhost:8088/test/ids/term
	取得表格 term 中的 ObjId 清單
- curl http://localhost:8088/test/ids/rds
	取得表格 rds 中的 ObjId 清單

## 項目

- API: /test/item/:tb/:id
	取得表格 :tb 中的項目 :id
- API: /test/item/:tb/:id/
	同上，有定位比較漂亮
- API: /test/items/:tb
	取得表格中所有項目
- API: /test/items/:tb/
	同上，有定位比較漂亮

### 範例

- curl http://localhost:8088/test/item/term/1 
- curl http://localhost:8088/test/item/term/1/ 
- curl http://localhost:8088/test/item/rds/1 
- curl http://localhost:8088/test/item/rds/1/ 
- curl http://localhost:8088/test/item/app/1 
- curl http://localhost:8088/test/item/app/1/ 

## status

- API: /test/licensed
	取得 status 中占 license 的 terminal 及 max license
- API: /test/licensed/
	同上，有定位比較漂亮
- API: /test/status
	取得 max licenses + status 資訊, 用來看 license
- API: /test/status/
	同上，有定位比較漂亮
- API: /test/check
	印出目前 pings + status
- API: /test/check
	同上，有定位比較漂亮

# 待驗證

## websocket

- API: /ws/post
	功能寫了，但是範例還沒寫

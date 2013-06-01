Conference Open Data
=============
一年365天月月有研討會，厚厚的議程表似乎沒有人特地整理成開放資料？
這個 repo 試著建立一個描述 conference 議程的格式，還請各位不吝 pull request 啊。

格式
----
* `/name`
* `/location`: string or 
	- `./name`
	- `./address`
	- `./longtitude`, `./latitude`
* `/agenda`: array of sessions. for each session,
	- `./name`
	- `./start`, `./end`: Unix timestamp of time
	- `./speakers`: string or dict. for each dict entry,
		+ key: speaker name
		+ value: array of titles / descriptions
	- `./location`: string, array of string, `*` (for broadcasted session), or `undefined` (for conference flow)

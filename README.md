Conference Open Data
=============
一年365天月月有研討會，厚厚的議程表似乎沒有人特地整理成開放資料？
這個 repo 試著建立一個描述 conference 議程的格式，還請各位不吝 pull request 啊。

格式
----
### 資料型別定義
* string / int / real
* entity（擁有固定屬性的 map）
* dict（擁有任意鍵/值的 map）
* time（int 或 real 的 Unix 時間戳記）
* tag（接受單一 string 或 string[]）
* 以上各種資料型別的陣列（ <i>object</i>[]）

* `/name` - string
* `/location`
	- string
	- entity
		+ `name`
		+ `address`
		+ `longtitude`, `latitude` - real : 經緯度座標
* `/url` - string
* `/agenda` - entity[]
	- `name`
	- `start`, `end` - time : 議程時間
	- `speakers`
		+ tag
		+ map（以 string : 講者為索引，string[] : 頭銜或敘述為值）
	- `location`
		+ tag
		+ string `"*"`（所有同時段場地）
	- `category` - tag
	- 其他中繼資料

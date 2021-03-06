# imas_cg_hash

アイドルのアルバムID（以下、ID）と画像ハッシュ（以下、ハッシュ）の相互変換を行うためのJSONファイル群です。

## JSONファイル

### id2hash.json

アイドルのIDからハッシュや特訓前後のID、ハッシュを取得するためのJSONファイルです。

アイドルのIDをキーに、[アイドルデータ形式](#アイドルデータ形式)のオブジェクトを取得できます。

#### 例
```json
"3521902": {"id": "3521902", "hash": "8eff69e4d99a16ba0ab8d8808b1dcfce", "name": "[ﾊﾂﾗﾂお嬢様･S]龍崎薫+", "idol_id": 137, "prev_id": "3421901", "prev_hash": "16879ab349989f30795c5a4aaf1f5b24", "id_family": ["3421901", "3521902"], "hash_family": ["16879ab349989f30795c5a4aaf1f5b24", "8eff69e4d99a16ba0ab8d8808b1dcfce"], "id_sibling": ["3321802", "3421801", "3521802"], "hash_sibling": ["eb7c81a65fd7e6298c860ee07e8d3d97", "7ac839de7d770abf38f7c1980d26faaa", "344f0b05bd380ef7190f06c0bc636968"]}
```

### hash2id.json

アイドルのハッシュからIDや特訓前後のID、ハッシュを取得するためのJSONファイルです。

アイドルのハッシュをキーに、[アイドルデータ形式](#アイドルデータ形式)のオブジェクトを取得できます。

#### 例
```json
"2175109269fe3e11706218748d8a2d9a": {"id": "3502902", "hash": "2175109269fe3e11706218748d8a2d9a", "name": "[ｻﾝﾌﾗﾜｰｲｴﾛｰ]龍崎薫+", "prev_id": "3402901", "prev_hash": "ae3ba85f888597f52c2744eeac3d9ace", "id_family": ["3402901", "3502902"], "hash_family": ["ae3ba85f888597f52c2744eeac3d9ace", "2175109269fe3e11706218748d8a2d9a"]}
```

## アイドルデータ形式

|キー         |意味                                |例                                                                                        |
|:------------|:-----------------------------------|:-----------------------------------------------------------------------------------------|
|id           |ID                                  |`"id": "3000401"`                                                                         |
|hash         |ハッシュ                            |`"hash": "6bd01496d9b00da9563c7e92b6a40257"`                                              |
|name         |名前                                |`"name": "龍崎薫"`                                                                        |
|idol\_id     |アイドルID                          |`"idol_id": 137`                                                                          |
|next\_id     |特訓後のID（特訓前、10進のみ）      |`"next_id": "3100402"`                                                                    |
|prev\_id     |特訓前のID（特訓後、10進のみ）      |`"prev_id": "3100401"`                                                                    |
|next\_hash   |特訓後のハッシュ（特訓前、10進のみ）|`"next_hash": "ce9be94eb3291a7f91c73a7824eb388c"`                                         |
|prev\_hash   |特訓前のハッシュ（特訓後、10進のみ）|`"prev_hash": "6bd01496d9b00da9563c7e92b6a40257"`                                         |
|id\_family   |特訓前後のIDの配列                  |`"id_family": ["3000401", "3100402"]`                                                     |
|hash\_family |特訓前後のハッシュの配列            |`"hash_family": ["6bd01496d9b00da9563c7e92b6a40257", "ce9be94eb3291a7f91c73a7824eb388c"]` |
|id\_sibling  |関連するID（I.C、スマイルなど）の配列|`"id_sibling": ["3421801", "3521802", "3421901", "3521902"]`                            |
|hash\_sibling|関連するハッシュの配列              |`"hash_sibling": ["7ac839de7d770abf38f7c1980d26faaa", "344f0b05bd380ef7190f06c0bc636968", "16879ab349989f30795c5a4aaf1f5b24", "8eff69e4d99a16ba0ab8d8808b1dcfce"]` |

## conflictサンプル

### 概要

単純な下記のようなcommitでconflictした状態のリポジトリ

```
                        conflict
 master   1---------3---@
              |         ^
              |         |
 branch01     +--2------+
```


### 実行方法


```sh
mkdir ${任意の場所}
cd ${任意の場所}
sh ${gen_conflict01.txtのパス}
```

で、上記の`@`の状態にいるリポジトリが作成される


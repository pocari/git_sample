## rebaseサンプル

### 概要
                        
 masterから派生したbranch01を一旦プルリクエストして、また反映していない場合に、
 branch01の続きに行いたい作業をbranch01から派生したbranch01-exで作業し、
 branch01がmasterにマージされた後にそこから、branch02を作成し、branch01-exを
 branch02にrebaseして、branch02の変更内容としてmasterにマージする直前まで

```
 master   1---------3-------------M--+---6--------------
              |                   ^  |
              |                   |  |
 branch01     \--2--+-------------+  |
                    |                |
 branch01-ex        \----4---5-----X |  (branch01-exはXで終了して、新たに4', 5'としてbranch02にrebaseする
                                     |
 branch02                            \-@---(4')--(5')--
```

 @にいるときに、

```sh
   git checkout branch01-ex
   git rebase branch02
```

 で、`branch01-ex`が`rebase`されるので、その後

```sh
   git checkout branch02
   git merge branch01-ex
```

 すると、branch01のプルリクがmasterにマージされる前に行ったcommit4, 5が、
 masterへのマージ後の状態から派生したブランチに対して行ったかのように見える


### 実行方法

```sh
mkdir ${任意の場所}
cd ${任意の場所}
sh ${gen_rebase01.txtのパス}
```

で、上記の`@`の状態にいるリポジトリが作成される


## find
### execオプション
- findで見つかったファイル・ディレクトリに対してコマンドを実行
- `{} +`を指定するとコマンドを一度に適用する
  ```
  // あり
  chmod -R 776 dir1 dir2 dir3 dir4
  // なし
  chmod -R 776 dir1
  chmod -R 776 dir2
  chmod -R 776 dir3
  chmod -R 776 dir4
  ```

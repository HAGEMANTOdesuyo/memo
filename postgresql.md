# PostgreSQL memo

## PostgreSQLに接続
- デフォルトのテーブルに接続
```
psql -d postgres
```

- テーブルとユーザを指定して接続
```
psql -d テーブル名 -U ユーザ名
```


- 接続解除
```
\q
```

## データベース
- データベース一覧
```
\l
```

- データベース選択
```
\c データベース名;
```

## テーブル
- テーブル一覧の表示（シーケンスも含む）
```
\d
```

- テーブル一覧の表示（テーブルのみ）
```
\dt
```

- テーブル構造の表示
```
\d テーブル名
```

- テーブルのオーナーの変更
```
alter table テーブル名 owner to オーナー名;
```

## ユーザー
- ユーザー一覧
```
\du
```

## スキーマ
- スキーマ一覧
```
\dn
```

## 一行のみのコマンドを実行
```
psql データベース名 -U postgres -c 'コマンド'
```

## シーケンス・シーケンス操作関数
```
id：デフォルト：nextval('sales_infos_id_seq'::regclass)
```
指定しなければ、idにnextval('sales_infos_id_seq'::regclass)が入る

```
select setval('sales_infos_id_seq',200);
select currval('sales_infos_id_seq');
```
https://www.postgresql.jp/document/8.0/html/functions-sequence.html

## 検索
- 大文字小文字区別せずに部分一致検索
```
select * from テーブル名 where カラム名 ILIKE '%キーワード%';
```
- 大文字小文字区別せずに部分一致検索&id降順&表示件数1  
```
select * from テーブル名 where カラム名 ILIKE '%キーワード%' order by id desc limit 1;
```

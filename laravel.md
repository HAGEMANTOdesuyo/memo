# laravel memo
- artisanコマンドの一覧表示
```
php artisan list
```
- Laravelプロジェクトの作成(version指定)
```
composer create-project laravel/laravel=6.18.* プロジェクト名
```

- DB接続確認
```
php artisan tinker
DB::connection()->getConfig();
DB::connection()->getPdo();
```

- Controller作成
  - 基本
```
php artisan make:controller <ControllerName>
```

  - Route::apiResourceに対応するController
```
php artisan make:controller Api/<ControllerName> --api
```

- migrationファイル作成
```
php artisan make:migration <filename>
```

- model作成
```
php artisan make:model Eloquents/<modelname>
```

- シーダー実行
  - 基本
```
php artisan db:seed
```
  - シーダーをマイグレーションごと巻き戻したいとき
```
php artisan migrate:refresh --seed
```

- migrate:refreshとmigrate:freshの違い
  - migrate:refresh
    down() を実行してから up() を実行する。なので down() の内容によっては up() の処理に影響を与える可能性がある。
  - migrate:fresh
    全テーブルをドロップしてから up() を実行する。 down() は実行されない。

- 自作クラスのパスを追加(tinkerで実行する時用)
```
composer dump-autoload
```

- ログ出力
```
Log::info('文字列');
Log::info(print_r($var, true));
※$varは非文字列
```

- トランザクションの張り方(手動)  


  - トランザクション開始  
    ここからDBの処理が始まる
    ```
    DB::beginTransaction();
    ```

  - コミット  
    ここまでの処理をデータベースに反映
    ```
    DB::commit();
    ```

  - ロールバック  
    処理を元に戻す
    try-catchのcatchにロールバックを入れることで、
    何らかのエラーが発生した場合、DBの処理をなかったことにする
    ```
    DB::rollback();
    ```

### npmパッケージ公開 手順メモ

#### npmユーザーの作成
- author情報の作成
```
$ npm set init.author.name "Kenji Kawanobe"
$ npm set init.author.email "kawake.kk@gmail.com"
$ npm set init.author.url "https://github.com/kenji7157"
```

- npmユーザーの登録
```
$ npm adduser 
Username: kenji7157
Password: *******
Email: (this IS public) kawake.kk@gmail.com
Logged in as kenji7157 on https://registry.npmjs.org/.
```

#### レポジトリの作成
- githubにnpmパッケージ用のレポジトリを作成
https://github.com/kenji7157/iamhappy

- 作業ディレクトリでcloneする
```
$ git clone git@github.com:kenji7157/iamhappy
```

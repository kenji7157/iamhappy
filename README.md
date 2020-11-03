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

- cloneする
```
$ git clone git@github.com:kenji7157/iamhappy
```
以降は[iamhappy]で作業をする

#### パッケージ情報の設定
```
$ npm init
```
全てデフォルトで作成

#### プログラムの作成
- index.jsの作成
```
$ touch index.js
```

```js
// index.js
function happy () {
  console.log('I am Happy.');
}

module.exports = {
  happy
};
```


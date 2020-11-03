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

#### ライセンスファイルの作成
- package.jsonのライセンス情報の修正
```json
...
  "license": "MIT",
...
```

- LICENSE.txtの作成
iamhappy配下に作成する
```
$ touch LICENSE.txt
```
内容は[The MIT License](https://opensource.org/licenses/MIT)を参照し作成  
[YEAR]と[COPYRIGHT HOLDER]を任意で書き換えておく

```txt
Copyright 2020 Kenji Kawanobe

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

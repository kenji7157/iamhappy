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

#### npmに公開
- リポジトリにタグを作成
```
$ git tag -a v1.0.0 -m "My first version v1.0.0"
```

- タグをpushする
```
$ git push origin tags/v1.0.0
```

- npmレジストリにログインしてemailを登録しておく
(手順1)[npm公式レジストリ](https://www.npmjs.com/email-edit )に[author情報の作成]で作成したアカウントでログインしておく。

(手順2)メールアドレスを改めて設定する。

(手順3)npmからメールが飛んでくるので認証する。

- npmへの公開
```
$ npm publish ./
npm notice 
npm notice 📦  iamhappy@1.0.0
npm notice === Tarball Contents === 
npm notice 82B   index.js    
npm notice 727B  package.json
npm notice 2.9kB README.md   
npm notice 1.1kB LICENSE.txt 
npm notice === Tarball Details === 
npm notice name:          iamhappy                                
npm notice version:       1.0.0                                   
npm notice package size:  2.0 kB                                  
npm notice unpacked size: 4.8 kB                                  
npm notice shasum:        add0e70067382c40b817f6d169f1b3be15b74a03
npm notice integrity:     sha512-RS/+v5gU6VjhB[...]HfeTcBNz2REHw==
npm notice total files:   4                                       
npm notice 
+ iamhappy@1.0.0
```
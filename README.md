# 高専学生食堂システム

## about

そのうち

Larvel を使用します

## install

### Composer

詳しくは[ここ](https://getcomposer.org/download/)を参照。

```Bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

これで、上のコマンドを使用した場所で`composer.phar`ができていることを確認すること。

そのファイルがあれば、Composer の機能を`php composer.phar`で使用できる。

### Laravel

詳しくは[ここ](https://readouble.com/laravel/5.8/ja/installation.html)を参照

以下上記コマンドを使用した場所で実行

```Bash
php composer.phar global require laravel/installer
```

これで、`$HOME/.composer/vendor/bin/laravel ...`で larvel コマンドが使えるようになる。

しかし、このままだとコマンド名が長いので、PATH を通す。

以下 Linax の話。

テキストエディタは自由

```Bash
emacs ~/.bash_profile
```

(どこでもいいけど、よくわからないのなら)一番最後の行に下の行を追記して、保存。

```Bash
PATH="$PATH:$HOME/.composer/vendor/bin"
```

その後以下のコマンドを実行

```Bash
source ~/.bash_profile
```

## git

このプロジェクトでは git を使うので、インストールする

詳しくは[ここ](https://git-scm.com/book/ja/v1/%E4%BD%BF%E3%81%84%E5%A7%8B%E3%82%81%E3%82%8B-Git%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)

ざっとコマンドの説明をしておく。

都度、email とパスワードが聞かれるかもしれないので、その時は入力する。

基本的な順序としては

1. git clone(最初しか使わない)
2. git checkout : 自分が開発するためにブランチを移動する
3. 開発
4. git add : 変更したファイルを指定する
5. git commit : コミットという単位で変更をローカルに保存する
6. git push : オンライン(リモート)に変更を保存

### clone

一番最初に web からプロジェクトをとってくるために使うコマンド

```Bash
git clone https://github.com/Kousuke-N/kosen-lanch-menu
```

## 開発

### 準備

プロジェクトがあるディレクトリ(.../kosen-lanch-menu)に移動してから、下のコマンドを実行。

```Bash
php artisan serve
```

その後`http://127.0.0.1:8000/`にアクセスして、以下のサイトが表示されたら、起動成功。

![image](https://bitstar.jp/blog/wp-content/uploads/2018/12/laravel_top-1.png))

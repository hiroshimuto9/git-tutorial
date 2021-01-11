## `git reset`

`git reset`には3種類のオプションが存在します。

* `git reset --soft`

* `git reset --mixed`

* `git reset --hard`

それぞれ影響を与える範囲は、以下のようになっています。

--soft：HEADの位置のみ

--mixed：HEADの位置・ステージ

--hard：HEADの位置・ステージ・作業ディレクトリ

※ステージ=インデックスです。

<div style="text-align: center;">
<img src="../images/worktree.jpg" alt="リポジトリ概念図">
</div>

### `--soft`

`--soft`は直前のcommitをやり直したときに便利です。

ローカルリポジトリにコミットしてしまったものを、ステージングエリアに戻します。

【使い方】

①`sample_2.html`を作成し、コミット

<div style="text-align: center;">
<img src="../images/commit3.jpg" alt="コミット画像">
</div>

②他にも修正したい箇所があったため、`git reset --soft HEAD^`でステージングエリアに巻き戻す。

<div style="text-align: center;">
<img src="../images/reset-soft.jpg" alt="リセットソフト画像">
</div>

<div style="text-align: center;">
<img src="../images/reset-soft-sourcetree.jpg" alt="リセットソフト画像">
</div>

そうすると、ステージングエリアに変更した内容が戻っていることが確認できます。


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

### `--mixed`

`--mixed`は`git add`でステージしたファイルを作業ディレクトリに戻すときに使われます。これは、commitしたもの、`add`でステージしたものどちらもが巻き戻ります。

【使い方】

①
`sample_2.html`を作成し、コミット
`sample_3.html`を作成し、ステージに`git add`

<div style="text-align: center;">
<img src="../images/add-commit.jpg" alt="git-addとコミット画像">
</div>


<div style="text-align: center;">
<img src="../images/git-add-commit-sourcetree.jpg" alt="git-add画像">
</div>

②`git reset --mixed HEAD`でステージしたものを取り消す。
※尚、オプション無しでも`--mixed`を実行したときと同じ結果が得られます。

<div style="text-align: center;">
<img src="../images/reset-mixed.jpg" alt="リセットミックス画像">
</div>

そうすると、作業ディレクトリにコミットしたものと、`git add`した内容が戻っていることが確認できます。

### `--hard`
`--hard`はステージングエリアにも作業ディレクトリにも残さず、コミットをまるごと消したいときに使われます。

【使い方】

①
`sample_2.html`を作成し、コミット
`sample_3.html`を作成し、ステージに`git add`

<div style="text-align: center;">
<img src="../images/add-commit.jpg" alt="git-addとコミット画像">
</div>

<div style="text-align: center;">
<img src="../images/git-add-commit-sourcetree.jpg" alt="git-add画像">
</div>

②`git reset --hard HEAD^`でステージしたもの、コミットしたものを取り消す。

<div style="text-align: center;">
<img src="../images/reset-hard.jpg" alt="リセットハード画像">
</div>

そうすると、ステージにも作業ディレクトリにも、今回の作業の内容は残らなくなることが確認できます。

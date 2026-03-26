# Lark講座 講師向けポータル（GitHub Pages）

講師向けの理念・カリキュラム・運営ルールをブラウザで閲覧するための静的サイトです。

## 公開URL（講師に共有）

| ページ | URL |
|--------|-----|
| **講師向けポータル（メイン）** | https://dekashacho.github.io/lark-instructor-guide/ |
| **L1〜L3 動画・課題マップ** | https://dekashacho.github.io/lark-instructor-guide/curriculum-map.html |
| **受講生向けコース全体像** | https://dekashacho.github.io/lark-instructor-guide/course-overview.html |
| **ルックアップと双方向関連（インフォグラフィック）** | https://dekashacho.github.io/lark-instructor-guide/lookup-vs-bidirectional.html |

## リポジトリ内ドキュメント（GitHub上で閲覧）

- [L1-L3_動画・課題統合マスター.md](./L1-L3_動画・課題統合マスター.md)
- [動画コンテンツ化_運営体制設計書.md](./動画コンテンツ化_運営体制設計書.md)

## デプロイ

`main` ブランチのルートが GitHub Pages の公開ソースです。`git push origin main` で更新が反映されます（反映まで1〜3分程度のことがあります）。

### 更新がブラウザに反映されないとき

1. **Cursor のこのフォルダと GitHub のクローンは別物**  
   ここ（`Lark講座ナレッジ/.../講師向けポータル/`）で HTML を直しただけでは、自動では `lark-instructor-guide` に入りません。リポジトリをクローンした場所の**ルート**に、更新した `lookup-vs-bidirectional.html` などをコピーしてから `git add` → `commit` → `push` してください。

2. **本当に新しいファイルが push されているか確認**  
   ターミナルで次を実行し、**1 行でもヒットすれば**本番HTMLに新セクションが載っています。何も出なければ、まだ古いファイルが配信されています。

   ```bash
   curl -sL "https://dekashacho.github.io/lark-instructor-guide/lookup-vs-bidirectional.html" | grep "違いを比較してみよう"
   ```

3. **ページ内の目印**  
   `lookup-vs-bidirectional.html` のフッターに **「ページ版: 2026-03-26（比較表・判断フロー・Q&A・まとめ）」** と出ていれば、スライド相当の追記版です。見えない場合はキャッシュではなく、**未デプロイまたは別URL**を見ている可能性が高いです。

4. **キャッシュ**  
   GitHub Pages は短い `max-age` のキャッシュがあります。シークレットウィンドウで開くか、URL の末尾に `?v=2` のようにクエリを付けて再読み込みしてください。

5. **GitHub の Pages 設定**  
   Settings → Pages で「Deploy from a branch」の **Branch が `main` / フォルダが `/ (root)`** になっているか確認してください（`/docs` だけ公開していると、ルートの HTML が使われません）。

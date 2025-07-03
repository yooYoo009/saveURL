# URL管理アプリ - PWA版

このアプリをデスクトップアプリとして使用するためのセットアップ手順です。

## セットアップ手順

### 1. アイコンファイルの生成
1. `icon-generator.html` をブラウザで開く
2. 「192x192アイコンをダウンロード」ボタンをクリックして `icon-192.png` を保存
3. 「512x512アイコンをダウンロード」ボタンをクリックして `icon-512.png` を保存
4. 両方のファイルをアプリのフォルダに配置

### 2. ローカルサーバーの起動
PWAとして動作させるには、HTTPSまたはlocalhostでの実行が必要です。

#### 方法1: Python（推奨）
```powershell
# Python 3がインストールされている場合
python -m http.server 8080

# 他のポートを使用する場合（8000が使用中の場合など）
python -m http.server 3000
python -m http.server 5000
python -m http.server 8888

# または Python 2の場合
python -m SimpleHTTPServer 8080
```

#### 方法2: Node.js
```powershell
# http-serverをインストール
npm install -g http-server

# サーバー起動（デフォルトポート8080）
http-server -p 8080

# 他のポートを使用する場合
http-server -p 3000
http-server -p 5000
```

#### 方法3: PowerShell（Windows 10/11）
```powershell
# IISがインストールされている場合
# または Visual Studio Code の Live Server 拡張機能を使用
```

### 3. ブラウザでアクセス
1. ブラウザで `http://localhost:8080` にアクセス（または使用したポート番号）
2. Chrome/Edge の場合、アドレスバーに「インストール」アイコンが表示されます
3. または右上の「アプリをインストール」ボタンをクリック

### 4. デスクトップアプリとして使用
- インストール後、デスクトップやスタートメニューからアプリを起動できます
- オフラインでも基本機能が使用可能です
- データはローカルストレージに保存されます

## 機能
- URLの追加・削除
- データの永続化（ローカルストレージ）
- オフライン対応
- デスクトップアプリとしてインストール可能
- レスポンシブデザイン

## トラブルシューティング

### PWAがインストールできない場合
1. HTTPSまたはlocalhost環境で実行していることを確認
2. ブラウザがPWAに対応していることを確認（Chrome、Edge、Firefox等）
3. アイコンファイル（icon-192.png、icon-512.png）が正しく配置されていることを確認

### アイコンが表示されない場合
1. `icon-generator.html` からアイコンを再ダウンロード
2. ファイル名が正しいことを確認（icon-192.png、icon-512.png）
3. ブラウザのキャッシュをクリア

## 技術的な詳細
- Service Worker によるオフライン対応
- Web App Manifest による PWA メタデータ
- Local Storage による データの永続化

# learning

このプロジェクトでは、Prismaを使用したデータベース管理を学習します。

## 📖 参考資料
Prisma公式ドキュメント: [Prisma Getting Started](https://www.prisma.io/docs/getting-started/quickstart-sqlite)

## 🛠️ セットアップ手順

### 1. リポジトリのクローン
```sh
git clone https://github.com/hakatas/learning.git
cd learning
```

### 2. 必要なパッケージのインストール
```sh
npm install
```

### 3. Prismaの初期化
```sh
npx prisma init
```
このコマンドを実行すると、`prisma` ディレクトリが作成され、`schema.prisma` ファイルが生成されます。

### 4. データベースのマイグレーション
```sh
npx prisma migrate dev --name init
```

### 5. Prisma Studioの起動（オプション）
Prisma Studioを使用すると、データベースをGUIで管理できます。
```sh
npx prisma studio
```

## 🚀 Prisma クエリの実行
Prisma Clientを使ってデータベース操作が可能です。以下の例は `index.js` での基本的なクエリです。

```javascript
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function main() {
  const allUsers = await prisma.user.findMany();
  console.log(allUsers);
}

main()
  .catch((e) => console.error(e))
  .finally(async () => {
    await prisma.$disconnect();
  });
```

## 📝 ライセンス
MIT


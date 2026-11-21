# Query by Program

## PHP
```
<?php
// PostgreSQLへの接続設定
$host = "localhost";
$port = "5432";
$dbname = "test_db";
$user = "username";
$password = "password";

try {
    // データベースに接続
    $dsn = "pgsql:host=$host;port=$port;dbname=$dbname";
    $pdo = new PDO($dsn, $user, $password);

    // SQL実行
    $sql = "select id, name from test_table";
    $stmt = $pdo->query($sql);

    // レコード取得
    $rows = $stmt->fetchAll(PDO::FETCH_ASSOC);

} catch (PDOException $e) {
    die("Database Error: " . htmlspecialchars($e->getMessage()));
}

// 取得したレコードを表形式で出力
for ($i = 0; $i < count($rows); $i++) {
    echo htmlspecialchars($rows[$i]["id"]) . "   " . htmlspecialchars($rows[$i]["name"]) . "\n";
```

## Python
```
import psycopg

conn = psycopg.connect("dbname=your_db user=your_user password=your_password host=localhost")
cur = conn.cursor()
cur.execute("SELECT * FROM users;")
print(cur.fetchall())
```


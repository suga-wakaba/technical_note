# Query by Program

## PHP
### db_config.php
```
<?php
$DB_HOST = "localhost";
$DB_PORT = "5432";
$DB_DBNAME = "test_db";
$DB_USER = "user";
$DB_PASSWORD = "password";
$DB_TABLE = "users";
```
### test.php
```
<?php
// １階層上に設定ファイルを配置（DocumentRoot外へのDB情報の保存を想定）
require_once __DIR__ . '/../db_config.php';

try {
    // データベースに接続
    $dsn = "pgsql:host=$DB_HOST;port=$DB_PORT;dbname=$DB_DBNAME";
    $pdo = new PDO($dsn, $DB_USER, $DB_PASSWORD);

    // SQL実行
    $sql = "select id, name from $DB_TABLE";
    $stmt = $pdo->query($sql);

    // レコード取得
    $rows = $stmt->fetchAll(PDO::FETCH_ASSOC);

} catch (PDOException $e) {
    die("Database Error: " . htmlspecialchars($e->getMessage()));
}

// 取得したレコードを表形式で出力
for ($i = 0; $i < count($rows); $i++) {
    echo htmlspecialchars($rows[$i]["id"]) . "   " . htmlspecialchars($rows[$i]["name"]) . "<br>\n";
}
```

## Python
```
import psycopg

conn = psycopg.connect("dbname=your_db user=your_user password=your_password host=localhost")
cur = conn.cursor()
cur.execute("SELECT * FROM users;")
print(cur.fetchall())
```


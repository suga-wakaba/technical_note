# Requirement packages

## Install
```
dnf install autoconf automake
```

## File Structure
```
.
├── calc-add.c      (プログラムのソースコード)
├── configure.ac    (configureスクリプトの生成ルール)
└── Makefile.am     (Makefileの生成ルール)
```

## Create Autoconf File
- File Name: `configure.ac`
- `.ac` is the file to generate `configure` file.
```
AC_INIT([calc-add], [1.0], [bug-report@example.com])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])

# Cコンパイラの存在チェック
AC_PROG_CC

# 出力するファイルの指定
AC_CONFIG_FILES([Makefile])
AC_OUTPUT
```

## Create Automake File
- File Name: `Makefile.am`
- `.ac` is the file to generate `Makefile.in` file.

```
# 実行ファイルの定義
bin_PROGRAMS = calc-add

# ソースファイルの指定
calc_add_SOURCES = calc-add.c
```

## Generate `configure` File
```
autoreconf -i
```


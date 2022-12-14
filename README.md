# xafs-schema


## 概要

日本XAFS研究会においてXAFSデータベースのメタデータ案(以後:XAFS20221212)が募集されています。

参考URL:  <https://www.jxafs.org/xafs-database/>

上記案に沿ってメタデータ記述を行っていくためには、メタデータ更新やバージョン管理、メタデータスキーマに沿ってメタデータが記述されているのかの確認、および、間違いがあった際の修正が柔軟にできること、がとても重要になります。

本プロジェクトではXAFS20221212メタデータ管理、メタデータスキーマ作成、およびメタデータスキーマを用いたメタデータ確認についての案をまとめました。

コメントなどありましたらmatumot@spring8.or.jpまでご連絡ください。



## メタデータ管理

さまざまなXAFSメタデータの追加・修正などを簡易に管理できるよう、エクセルファイルを用います。

XAFS20221212でのエクセルファイルは[こちら](./draft/20221212/metadata_schema-xafs)よりアクセスできます。

仕様はREADMEシートをご参照ください。各カテゴリのメタデータがそれぞれ定義され、簡易に管理できるようになっています。



## メタデータスキーマ確認

メタデータスキーマ確認についてですが、以下を用いた方法をそれぞれご紹介します。

- [Visual Studio Codeを用いた方法 (YAML)](./README_vscode.md)
- [Pythonを用いた方法 (YAML/Python)](./README_python.md)



## License

Apache License 2.0

## Author

Copyright (C) 2022 Takahiro Matsumoto (matumot@spring8.or.jp)

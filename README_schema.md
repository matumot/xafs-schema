# メタデータスキーマ作成方法



## Python環境構築

condaを利用した場合、以下の手順で行います。

```
> conda create -n xafs-schema python=3.10
> conda activate xafs-schema
(xafs-schema)> pip install -r requirements.txt
```



## メタデータスキーマ作成方法

下記のようにメタデータ管理のエクセルファイルを指定してメタデータスキーマファイル (jsonshema)を作成します。

```
(xafs-schema) >python generate_xafs_schema.py draft/20221212/metadata_schema-xafs.xlsx
... input draft/20221212/metadata_schema-xafs.xlsx
... output ./schema/xafs-schema.json
... output ./schema/xafs-schema-none-ok.json
```

* xafs-schema.json
  * metadata_schema-xafs.xls に従って作成された jsonschemaファイルです。 
* xafs-schema-none-ok.json　　**利用は非推奨**
  * 同様に、metadata_schema-xafs.xls に従って作成された jsonschemaファイルですが、数値が指定されたメタデータで値を入力しなくても (None）エラーが発生しないようになっています。


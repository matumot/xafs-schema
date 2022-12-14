# Pythonを用いたメタデータスキーマ確認(YAML/Python)



## Python環境構築

condaを利用した場合、以下の手順で行います。

```
> conda create -n xafs-schema python=3.10
> conda activate xafs-schema
(xafs-schema)> pip install -r requirements.txt
```



## 利用方法

config.yml に指定するスキーマファイル (or URL)を指定します。

```yaml
schema_path: https://raw.githubusercontent.com/matumot/xafs-schema/main/draft/20221212/xafs-schema.json
#schema_path: ./draft/20221212/xafs-schema.json
#schema_path: ./draft/202221212/xafs-schema-none-ok.json
```



以下に示すように **check_schema.py** スクリプトを用いてメタデータYAMLの整合性を確認します。

引数には対象となるメタデータファイル (YAML or Python)を指定します。

```
(xafs-schema)> check_schema.py example/metadata-xafs.yml
... input metadata: example/metadata-xafs.yml
... schema path: ./draft/20221212/xafs-schema.json
... get schema from ./draft/20221212/xafs-schema.json
... check example/metadata-xafs.yml: OK
```



もし、不整合がある際は、以下のようにエラーについて表示されます。

```
(xafs-schema)>python check_schema.py example/jxs-xafsDB-wg-20221206.yml
... input metadata: example/jxs-xafsDB-wg-20221206.yml
... schema path: ./draft/20221212/xafs-schema.json
... get schema from ./draft/20221212/xafs-schema.json
... check example/jxs-xafsDB-wg-20221206.yml: NG
 ==> Error()
     message = {
    "error": "Invalid metadata schema",
    "details": {
        "example\\jxs-xafsDB-wg-20221206.yml": [
            "[instrument.monochromator.detail.groove_density] None is not of type 'number'",
            "[instrument.monochromator.detail.groove_depth] None is not of type 'number'",
            "[instrument.monochromator.detail.groove_deviation_angle] None is not of type 'number'",
            "[measurement.I0.ammeters.gain] '10^6' is not of type 'number'",
            "[measurement.detector.0.processing_lines.0.conversion_factor.value] '1e8' is not of type 'number'",
            "[measurement.detector.0.processing_lines.0.processors.0.gain.value] '1e6' is not of type 'number'",
            "[measurement.detector.0.processing_lines.0.processors.0.time_constant.value] '1e-3' is not of type 'number'",
            "[measurement.detector.0.processing_lines.0.processors.1.gain.value] '1e8' is not of type 'number'",
            "[measurement.section.blocks.block.0.dwell_time] None is not of type 'number'",
            "[measurement.tune.tune_energy] None is not of type 'number'",
            "[sample.shape.size.value] '2-5' is not of type 'number'"
        ]
    }
}
```


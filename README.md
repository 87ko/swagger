参考 URL

SPDX：https://spdx.org/licenses/

データ型

```yml
components:
    schemas:
        ## データ型サンプル
        SampleCommon:
            type: string
            format: email
            description: "str" #共通-データ型の説明
            default: "default" #共通-デフォルト値
            nullable: true #共通-null許容するかどうか
            example: "abc" #共通-サンプル
            deprecated: false #共通-有効化どうか
        SampleInt:
            type: integer
            format: int32
            multipleOf: 10 #integer-指定数の倍数か？
            maximum: 100 #integer- 最大値
            exclusiveMaximum: false #integer-最大値を含まないかどうか true x<100, false x<=100
            minimum: 10 #integer- 最小値
            exclusiveMinimum: false #integer専用-最小値を含むか
        SampleString:
            type: string
            format: email
            minLength: 0 #string- x>=0
            maxLength: 100 #string- x<=100
        SampleBoolean:
            type: boolean
        SampleObject:
            type: object
            properties: #object-プロパティ定義
                name: { type: string }
                dob: { type: string, format: date }
            additionalProperties: true #object-スキーマ以外のプロパティを許すかどうか
            required: #object- 必須プロパティを配列で指定
                - name
            minProperties: 2 #object-最小プロパティ数
            maxProperties: 2 #object-最大プロパティ数
        SampleArray:
            type: array
            items: { type: string } #array-配列に入れられるスキーマを指定
            minItems: 0 #array-最小個数
            maxItems: 5 #array-最大個数
            uniqueItems: true #array-配列内で値の重複をゆるかどうか
        SampleEnum:
            type: string #enumに格納するタイプを指定
            enum: ["red", "blue", "yello"]
```

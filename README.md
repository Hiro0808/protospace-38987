#　データベース設計

##　users　テーブル

|Column              |Type      |Options                              |
|--------------------|----------|-------------------------------------|
|email               |string    |NULL:false, ユニーク制約               |
|encrypted_password  |string    |NULL:false                           |
|name                |string    |NULL:false                           |
|profile             |text      |NUll:false                           |
|occupation          |text      |NUll:false                           |
|position            |text      |NUll:false                           |

### Association

-has_many : prototypes
-has_many : comments


## prototypes テーブル

|Column              |Type      |Options                              |
|--------------------|----------|-------------------------------------|
|title               |string    |NULL:false                           |
|catch_copy          |text      |NULL:false                           |
|concept             |text      |NULL:false                           |
|user                |references|NUll:false,foreign_key:true          |

### Association

-has_many : comments
-belongs_to : user

## comments テーブル

|Column              |Type      |Options                              |
|--------------------|----------|-------------------------------------|
|content             |text      |NULL:false                           |
|prototype           |references|NUll:false,foreign_key:true          |
|user                |references|NUll:false,foreign_key:true          |

### Association

-belongs_to : prototype
-belongs_to : user
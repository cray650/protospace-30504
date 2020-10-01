# README

#テーブル設計

## users テーブル

| Column     | Type   | Options  |
| ---------- | ------ | ---------|
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association

- has_many :comments
- has_many :prototypes


## prototypes テーブル

| Column     | Type       | Options                     |
| ---------- | ---------- | --------------------------- |
| title      | string     | NOT NULL                    |
| catch_copy | text       | NOT NULL                    |
| concept    | text       | NOT NULL                    |
| user       | references | NOT NULL, foreign_key: true |

### Association
- has_many :comments
- belongs_to :users

## comments テーブル

| Column     | Type       | Options                     |
| ---------- | ---------- | --------------------------- |
| title      | string     | NOT NULL                    |
| catch_copy | text       | NOT NULL                    |
| concept    | text       | NOT NULL                    |
| user       | references | NOT NULL, foreign_key: true |

### Association
- belongs_to :users
- belongs_to :prototypes

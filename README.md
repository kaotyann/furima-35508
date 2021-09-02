# テーブル設計

## users テーブル
| Column             | Type   | Options                  |
| ------------------ | ------ | -------------------------|
| nickname           | string | null: false              |
| email              | string | unique:true, null: false |
| encrypted_password | string | null: false              |
| first_name         | string | null: false              |
| last_name          | string | null: false              |
| last_name_kana     | string | null: false              |
| birthday           | date   | null: false              |
### Association
- has_many :items
- has_many :buys



## items テーブル
| Column             | Type      | Options     |
| ------------------ | ----------| ----------- |
| image              |           |             |
| name               | string    | null: false |
| description        | text      | null: false |
| category_id        | integer   | null: false |
| item_status_id     | integer   | null: false |
| delivery_fee_id    | integer   | null: false |
| prefecture_id      | integer   | null: false |
| delivery_fee_id    | integer   | null: false |
| price              | integer   | null: false |
| user               | references|             |
### Association
- belongs_to :user
- has_one :buys



## buys テーブル
| Column             | Type      | Options     |
| ------------------ | ----------| ----------- |
| user               | references|             |
| item               | references|             |
### Association
- belongs_to :user
- belongs_to :item
- has_one : addresses



## addresses テーブル
| Column             | Type      | Options     |
| ------------------ | ----------| ----------- |
| post_code          | string    | null: false |
| prefecture         | integer   | null: false |
| city               | string    | null: false |
| address            | string    | null: false |
| building           | string    |             |
| phone_number       | string    | null: false |
| buy                | references|             |
### Association
- belongs_to :buys






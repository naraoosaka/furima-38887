
# README
# テーブル設計

## users テーブル

| Column                | Type   | Options     |
| ------------------    | ------ | ----------- |
| nickname              | string | null: false |
| email                 | string | null: false,unique: true|
| encrypted_password    | string | null: false|
| family_name           | string | null: false |
| name                  | string | null: false |
| family_name_kana     | string | null: false |
| name_kana            | string | null: false |
| birthday              | date | null: false |



### Association

- has_many :items
- has_many :orders



## orders テーブル

| Column     | Type       | Options     |
| ------     | ------     | ----------- |
| item      | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

### Association

- belongs_to :item
- belongs_to :user
- has_one : delivery



## deliveries テーブル

| Column         | Type       | Options                        |
| -------        | ---------- | ------------------------------ |
| post_number    | string | null: false |
| prefecture_id    | integer | null: false |
| city           | string | null: false |
| address        | string | null: false |
| build_name     | string | 
| tel            | string | null: false |
| order         | references | null: false, foreign_key: true |


### Association

- belongs_to :order

## items テーブル

| Column                | Type    | Options     |
| ---------------   --- | ------  | ----------- |
| items_name            | string  | null: false |
| category_id           | integer | null: false |
| situation_id          | integer | null: false |
| delivery_fee_id       | integer | null: false |
| prefecture_id               | integer | null: false |
| spendday_id               | integer | null: false |
| price                 | integer | null: false |
| items_explain         | text  | null: false |
| user                  | references | null: false, foreign_key: true |

### Association

- belongs_to :user
- has_one :order

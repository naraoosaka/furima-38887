
# README
# テーブル設計

## users テーブル

| Column                | Type   | Options     |
| ------------------    | ------ | ----------- |
| nickname              | string | null: false |
| email                 | string | null: false |
| encrypted_password    | string | null: false |
| family_name           | string | null: false |
| name                  | string | null: false |
| family_name(kana)     | string | null: false |
| name(kana)            | string | null: false |
| birthday              | integer | null: false |



### Association

- has_many :item
- has_many :order



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
| post-number    | string | null: false |
| prefecture     | string | null: false |
| city           | string | null: false |
| address        | string | null: false |
| build_name     | string | null: false |
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
| delivery-fee_id       | integer | null: false |
| area_id               | integer | null: false |
| days_id               | integer | null: false |
| price                 | integer | null: false |
| items_explain         | string  | null: false |
| user                  | references | null: false, foreign_key: true |

### Association

- belongs_to :item
- has_one :order

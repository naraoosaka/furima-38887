
# README
# テーブル設計

## users テーブル

| Column                | Type   | Options     |
| ------------------    | ------ | ----------- |
| nickname              | string | null: false |
| email                 | string | null: false |
| encrypted_password    | string | null: false |


### Association

- has_many :items
- has_many :orders



## orders テーブル

| Column     | Type       | Options     |
| ------     | ------     | ----------- |
| name       | string     | null: false |
| credit     | text       | null: false |
| users      | references | null: false, foreign_key: true |

### Association

- belongs_to :items
- belongs_to :users
- has_one : delivery



## deliveries テーブル

| Column         | Type       | Options                        |
| -------        | ---------- | ------------------------------ |
| post-number    | string | null: false |
| prefecture     | string | null: false |
| city           | string | null: false |
| address        | string | null: false |
| build-name     | string | null: false |
| tel            | string | null: false |
| orders         | references | null: false, foreign_key: true |


### Association

- belongs_to :orders

## items テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| items-name         | string | null: false |
| category           | string | null: false |
| situation          | string | null: false |
| delivery-fee       | string | null: false |
| area               | string | null: false |
| days               | string | null: false |
| price              | string | null: false |
| items-explain      | string | null: false |
| users              | references | null: false, foreign_key: true |

### Association

- belongs_to :items
- has_one :orders

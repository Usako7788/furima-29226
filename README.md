## users
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| name-zen | string | null: false |
| name-kana| string | null: false |
| days     | date   | null: false |
- has_many :items
- has_many :orders

## items
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| name     | string     | null: false |
| category | integer    | null: false |
| status   | integer    | null: false |
| charge   | integer    | null: false |
| source   | integer    | null: false |
| price    | integer    | null: false |
| users-id | references | null: false, foreign_key: true |
- belongs_to :user
- has_one :done

## done
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| items-id | references | null: false, foreign_key: true|
| buyer    | string     | null: fakse |
| to-adress| string     | null: false |
- berongs_to :item
- has_one :order

## order
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| item-id  | references | null: false, foreign_key: true|
| users-id | references | null: false, foreign_key: true|
| orice    | integer    | null: false |
- berongs_to :done
- berongs_to :user


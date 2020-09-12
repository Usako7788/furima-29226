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
| image    | string     | null: false |
| name     | string     | null: false |
| info     | text       | null: false |
| category | integer    | null: false |
| status   | integer    | null: false |
| charge   | integer    | null: false |
| source   | integer    | null: false |
| price    | integer    | null: false |
| user     | references | null: false, foreign_key: true |
- belongs_to :user
- has_one :done

## done
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| item     | references | null: false, foreign_key: true|
| buyer    | string     | null: fakse |
- belongs_to :item
- has_one :order

## payment
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| done     | reference  |null: false, foreign_key: true|
| price    | integer    | null: false |
- belongs_to :done


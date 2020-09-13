## users
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| name-first | string | null: false |
| name-last | string | null: false |
| name-first-kana | string | null: false |
| name-last-kana | string | null: false |

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
| user     | references | null: false, foreign_key: true |
- belongs_to :item
- belongs_to :user
- has_one :order

## payment
| Column   | Type       | Options     |
| -------- | ---------- | ----------- |
| done     | reference  |null: false, foreign_key: true|
| Prefectures | integer    | null: false |
| cities　| integer    | null: false |
| address　| integer    | null: false |
| Building-number | integer | null: false |
| postal-code　| integer    | null: false |
| phone-number| integer    | null: false |
- belongs_to :done


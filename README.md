## users
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |
| name-zen | string | null: false |
| name-kana| string | null: false |
| days     | string | null: false |
- has_many :items
- has_many :oder

## items
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| category | string | null: false |
| status   | string | null: false |
| charge   | integer| null: false |
| source   | string | null: false |
| price    | integer| null: false |
| users-id | string | null: false |
- berongs_to :users
- has_one :done

## done
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| items-id | string | null: false |
| buyer    | string | null: fakse |
| to-adress| string | null: false |
- berongs_to :items
- has_one :oder

## oder
| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| item-id  | string | null: false |
| users-id | string | null: false |
| orice    | integer| null: false |
- berongs_to :done
- berongs_to :users


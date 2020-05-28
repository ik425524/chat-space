# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

## groups_users テーブル

| Column   | Type    | Options                        |
| -------- | ------- | ------------------------------ |
| user_id  | integer | null: false, foreign_key: true |
| group_id | integer | null: false, foreign_key: true |

###Association

- references :group
- references :user

## message テーブル

| Column   | Type    | Options |
| -------- | ------- | ------- |
| body     | text    |         |
| image    | string  |         |
| group_id | integer |         |
| user_id  | integer |         |

###Association

-references:group
-references:user

## user テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |

###Association

has_many :groups

## group テーブル

| Column     | Type   | Options |
| ---------- | ------ | ------- |
| group_name | string |         |

###Association

-has_many :users

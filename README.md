# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

## groups_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| group  | references | null: false, foreign_key: true |

###Association

- belongs_to :group
- belongs_to :user

## messages テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| body   | text       |                                |
| image  | string     |                                |
| group  | references | null: false, foreign_key: true |
| user   | references | null: false, foreign_key: true |

###Association

-belongs_to :group
-belongs_to :user

## users テーブル

| Column   | Type   | Options     |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |

###Association

-has_many :groups,through: :groups_users
-has_many :groups_users
-has_many :messages

## groups テーブル

| Column | Type   | Options |
| ------ | ------ | ------- |
| name   | string |         |

###Association
-has_many :users,through: :groups_users
-has_many :groups_users
-has_many :messages

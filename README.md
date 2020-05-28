# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

- Ruby version

- System dependencies

- Configuration

- Database creation

- Database initialization

- How to run the test suite

- Services (job queues, cache servers, search engines, etc.)

- Deployment instructions

- ...

## groups_users テーブル

| Column   | Type    | Options                        |
| -------- | ------- | ------------------------------ |
| user_id  | integer | null: false, foreign_key: true |
| group_id | integer | null: false, foreign_key: true |

###Association

- belongs_to :group
- belongs_to :user

## message テーブル

| Column   | Type    | Options |
| -------- | ------- | ------- |
| body     | text    |         |
| image    | string  |         |
| group_id | integer |         |
| user_id  | integer |         |

###Association

-belongs_to :group
-belongs_to :user

## user テーブル

| Column       | Type    | Options                        |
| ------------ | ------- | ------------------------------ |
| name         | string  | null: false                    |
| email        | string  | null: false                    |
| password     | string  | null: false                    |
| groups_users | integer | null: false, foreign_key: true |

###Association

- has_many :groups_users
- has_many :message

## group テーブル

| Column       | Type   | Options                        |
| ------------ | ------ | ------------------------------ |
| group_name   | string |                                |
| groups_users | string | null: false, foreign_key: true |

###Association

- has_many :groups_users
- has_many :massage

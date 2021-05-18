# README

### usersテーブル
|column            |types |Options                |
|------------------|------|-----------------------|
|email             |string |null: false,unique:true|
|encrypted_password|string |null: false            |
|family_name       |string |null: false            |
|first_name        |string |null: false            |
|family_name_kana  |string |null: false            |
|first_name_kana   |string |null: false            |
|birthday          |date   |null: false            |
|department_id     |integer|null: false            |


### Association
has many :room_users
has many :

### postsテーブル
|column          |types         |Options                     |
|----------------|--------------|----------------------------|
|name            |string        |null: false                 |
|department_id   |integer       |null: false            |
|text            |text          |null: false                 |
|event_month     |integer       |null: false                 |
|event_day       |integer       |null: false                 |
|event_place     |integer       |null: false                 |
|user            |references    |foreign_key: true           |

### Association
belongs_to :user
has_one :buy

## rooms テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association

- has_many :room_users
- has_many :users, through: room_users
- has_many :messages

## room_users テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| user   | references | null: false, foreign_key: true |
| room   | references | null: false, foreign_key: true |

### Association
- belongs_to :room
- belongs_to :user

## messages テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| content | string     |                                |
| user    | references | null: false, foreign_key: true |
| room    | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user




This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

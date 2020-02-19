# README

# chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :message
- has_many :group

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false|
|username|string|null: false|
### Association
- has_many :message
- has_many :user

## messageテーブル
|body|text|null: false|
|image|string|
|group_id|null: false, foreign_key: true|
|user_id|null: false, foreign_key: true|

### Association
- has_many :user
- has_many :group

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user

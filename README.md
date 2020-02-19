# README

# chat-space DB設計
## userテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :messages
- has_many :groups

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messagess
- has_many :users

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|null: false, foreign_key: true|
|user_id|null: false, foreign_key: true|

### Association
- has_many :users
- has_many :groups

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
# README

# chat_space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups,  through:  :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user|references|foreign_key: true|
|group|references|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :messages
- has_many :groups_users
- has_many  :users,  through:  :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group|references|foreign_key: true|
|user|references|foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

#README
## how to use GitHub Desktop
## how to use git revert


# Obentou DB設計
## ricesテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :massages
- has_many :groups, through :groups_users
- has_many :groups_users
## noodlesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Asssociation
- belongs_to :user
- belongs_to :group

## one_dishesテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
### Association
- has_many :users, through :groups_users
- has_many :messages
- has_many :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|reference|null: false, foreign_key: true|
|user_id|reference|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


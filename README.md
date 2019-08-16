## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false,index: true|

### Association
- has_many :groups_users
  has_many :groups, through: :groups_users
- has_many :massages


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
  belongs_to :user

  ## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false|
|name|string|null: false|

### Association
　has_many :users, through: :groups_users
　has_many :groups_users
　has_many :messages

## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
|body|text||
|image|string||

### Association
- belongs_to :group
- belongs_to :user
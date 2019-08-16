## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false,index: true|

### Association
- has_many :groups_users
  has_many :groups, through: :groups_users
- has_many :massages


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
  belongs_to :user


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|
|body|text|foreign_key: true|
|image|string|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
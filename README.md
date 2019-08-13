## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|text|null: false, foreign_key: true|
|e-mail|text|null: false, foreign_key: true|
|pass|text|null: false, foreign_key: true|

### Association
- has_many :group
- has_many :massage


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|text|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- has_many :user
- has_many :massage


## massagesテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|date|integer|null: false, foreign_key: true|
|body|text|null: false, foreign_key: true|
|image|string|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
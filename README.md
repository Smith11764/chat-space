## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
--------------------------------------------------

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|index:true, null: false, unique true|
|e-mail|string|null: false, unique:true|

### Association
- has_many :groups, through: :members
- has_many :members
- has_many :messages

--------------------------------------------------
## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null: false, unique: true|

### Association
- has_many :users, though: :members
- has_many :members
- has_many :messages

--------------------------------------------------
## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|sentence|text||
|image|string||
|group_id|references|foreign_key: true|
|user_id|references|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



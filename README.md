## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user|references|null: false, foreign_key: true|
|group|references|null: false, foreign_key: true|

### Association
- belongs_to :group, through: :members
- belongs_to :user
--------------------------------------------------

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|index:true, null: false, unique true|
|e-mail|string|null: false, unique:true|

### Association
- has_many :groups
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
|sentence|text|null: false|
|image|string||
|group|references|foreign_key: true|
|user|references|foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user



# テーブル設計

## usersテーブル
| Column             | Type    | Option                   |
| ------------------ | ------- | ------------------------ |
| nickname           | string  | null: false              |
| email              | string  | null: false, unique: true|
| encrypted_password | string  | null: false              |
| name               | string  | null: false              |
| birthday           | string  | null: false              |

### Association

- has_many  :tweets
- has_many  :coments

## tweetsテーブル
| Column             | Type       | Option                         |
| ------------------ | ---------- | ------------------------------ |
| text               | text       | null: false                    |
| user               | references | null: false, foreing_key: true |
| comment            | references | null: false, foreing_key: true |

### Association

- belongs_to  :user
- has_many    :comments

## commentsテーブル
| Column             | Type       | Option                         |
| ------------------ | ---------- | ------------------------------ |
| text               | text       | null: false                    |
| user               | references | null: false, foreing_key: true |
| tweet              | references | null: false, foreing_key: true |

### Association

- belongs_to  :user
- belongs_to  :tweet
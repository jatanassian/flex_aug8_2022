# Database Design

## Most important part of a web app

- Front end (UI)
- Backend
- Database

Database is the most important. Front end and Back end can be rebuilt.
Example" Facebook loses their database (users, posts, comments...)
Important keep it secure and design it properly

## Inside a database

1. Database
2. Tables
3. Columns / Fields
4. Rows / Records

## Naming conventions

For PostgreSQL

### Tables

- plural usually
- snake_case
- no convention lower or uppercase
  pets, Pets, other_tables

### Columns

- singular

pets

- id or pet_id
- name
- breed
- age
- color

owners

- id
- name

## Types of relationships

### One to One

user

- id
  - Primary Key (PK) | unique identifier
- name

user_profiles

- id
- user_id
  - Foreign Key (FK)
- profile_picture
- biography

### One to Many

pets

- id (PK)
- owner_id (FK)
- name
- breed
- age
- color

owners

- id (PK)
- name

### Many to Many

pets

- id (PK) | serial (auto-incrementing)
- name | text | NOT NULL
- breed | text
- age | integer
- color | text

pets_owners

- id
- pet_id (FK)
- owner_id (FK)

owners

- id (PK)
- name

## Data Types

- Numeric
- Characters
- Date
- Monetary
- Boolean

## Design concepts

- Avoid enums, arrays
- Required fields

```HTML
<form>
  <input type="email" required />
</form>
```

- default values
  user
- is_admin default:false

- data deletion?
  - soft delete:

users

- id
- name
- is_active: false

deleted_users

- id
- name

- calculated fields (composite type): let your front/back end do it

## Book store

books

- id
- name
- price
- quantity
- published_date

publishers

- id
- name

genres

- id
- type

authors

- id
- name

order

- id
- book_id
- customer_id

customers

- id
- name
- email
- phone
- address

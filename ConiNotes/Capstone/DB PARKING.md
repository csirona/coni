Certainly! Here's the table information in Markdown format with a focus on foreign keys:

### `users` Table

| Column | Type | Description |
| --- | --- | --- |
| id | INTEGER | The primary key of the users table. |
| username | VARCHAR(255) | The username of the user. |
| email | VARCHAR(255) | The email address of the user. |
| hashed_password | VARCHAR(255) | A hashed representation of the user's password. |

### `wallets` Table

| Column | Type | Description |
| --- | --- | --- |
| id | INTEGER | The primary key of the wallets table. |
| user_id | INTEGER (FK references users.id) | A foreign key that references the `id` column in the `users` table. It associates a wallet with a specific user. |
| balance | FLOAT | The balance in the wallet. |

### `cards` Table

| Column | Type | Description |
| --- | --- | --- |
| id | INTEGER | The primary key of the cards table. |
| user_id | INTEGER (FK references users.id) | A foreign key that references the `id` column in the `users` table. It associates a card with a specific user. |
| card_number | VARCHAR(255) | The card number associated with the user. |

### `cars` Table

| Column | Type | Description |
| --- | --- | --- |
| id | INTEGER | The primary key of the cars table. |
| user_id | INTEGER (FK references users.id) | A foreign key that references the `id` column in the `users` table. It associates a car with a specific user. |
| license_plate | VARCHAR(255) | The license plate of the car. |

### `parking_history` Table

| Column | Type | Description |
| --- | --- | --- |
| id | INTEGER | The primary key of the parking_history table. |
| car_id | INTEGER (FK references cars.id) | A foreign key that references the `id` column in the `cars` table. It associates a parking record with a specific car. |
| date | DATETIME | The date and time of the parking record. |

In this Markdown format, I've explicitly marked the foreign keys and the referenced columns in parentheses (e.g., `user_id | INTEGER (FK references users.id)`). This format makes it clear which columns are foreign keys and which tables they reference.
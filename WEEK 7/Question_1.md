### Before Normalization:

| OrderID | CustomerName | CustomerPhone | ItemsPurchased                   | TotalAmount |
| ------- | ------------ | ------------- | -------------------------------- | ----------- |
| 1       | John Doe     | 555-1234      | "Laptop - $1000, Mouse - $20"    | $1020       |
| 2       | Jane Smith   | 555-5678      | "Keyboard - $50, Monitor - $300" | $350        |
| 3       | John Doe     | 555-1234      | "Headphones - $80"               | $80         |

### 1NF:

ItemsPurchased is a multivalued and composite attribute so we will separate it in another table with the primary key (OrderID) as a foreign key

| OrderID (PK) | CustomerName | CustomerPhone | TotalAmount |
| ------------ | ------------ | ------------- | ----------- |
| 1            | John Doe     | 555-1234      | $1020       |
| 2            | Jane Smith   | 555-5678      | $350        |
| 3            | John Doe     | 555-1234      | $80         |

| OrderID (FK) | Item (FK)  |
| ------------ | ---------- |
| 1            | Laptop     |
| 1            | Mouse      |
| 2            | Keyboard   |
| 2            | Monitor    |
| 3            | Headphones |

| Item (PK)  | Price |
| ---------- | ----- |
| Laptop     | $1000 |
| Mouse      | $20   |
| Keyboard   | $50   |
| Monitor    | $300  |
| Headphones | $80   |

### 2NF:

It satisfies the 2NF

### 3NF:

There is a transitive function dependency where CustomerPhone depends on CustomerName depends on OrderId

| OrderID (PK) | CustomerName (FK) | TotalAmount |
| ------------ | ----------------- | ----------- |
| 1            | John Doe          | $1020       |
| 2            | Jane Smith        | $350        |
| 3            | John Doe          | $80         |

| OrderID (FK) | Item (FK)  |
| ------------ | ---------- |
| 1            | Laptop     |
| 1            | Mouse      |
| 2            | Keyboard   |
| 2            | Monitor    |
| 3            | Headphones |

| Item (PK)  | Price |
| ---------- | ----- |
| Laptop     | $1000 |
| Mouse      | $20   |
| Keyboard   | $50   |
| Monitor    | $300  |
| Headphones | $80   |

| CustomerName (PK) | CustomerPhone |
| ----------------- | ------------- |
| John Doe          | 555-1234      |
| Jane Smith        | 555-5678      |

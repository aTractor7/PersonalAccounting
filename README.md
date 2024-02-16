# Personal Accouting

Personal Accouting is a comprehensive tool for managing personal finances, including transactions, accumulations,
and financial arrangements. It provides features for tracking expenses, incomes, and managing various financial entities.

## Environment Requirements
- Java JDK 17+
- Maven 3.6+
- MySQL 8.0+

## Functionality
- Transaction tracking
- Accumulation management
- Financial arrangement handling
- Ability to categorize transactions and accumulations
- Storage of financial data securely

## API Endpoints

### Authentication
- `POST /auth/registration`: Register a new user.
- `GET /auth/`: Retrieve register user if it exist.
  - Request Body:
    ```json
    {
      "name": "example_name",
      "password": "password123",
      "email": "example@email.com"
    }
    ```

### Transactions
- `GET /transaction`: Retrieve all transactions.
- `GET /transaction/{id}`: Retrieve a specific transaction by ID.
- `POST /transaction`: Create a new transaction.
- `PUT /transaction/{id}`: Update an existing transaction.
- `DELETE /transaction/{id}`: Delete a transaction by ID.
  - Request Body for POST & PUT:
    ```json
    {
      "sum": 100,
      "comment": "Example transaction",
      "category": "FOOD_AND_DRINKS",
      "endDate": "2025-01-01 00:00:00",
      "refill": false,
      "periodic": false
    }
    ```

### Accumulations
- `GET /accumulation`: Retrieve all accumulations.
- `GET /accumulation/{id}`: Retrieve a specific accumulation by ID.
- `POST /accumulation`: Create a new accumulation.
- `PUT /accumulation/{id}`: Update an existing accumulation.
- `PUT /transaction/{id}/payment`: Credit the payment.
- `PUT /transaction/{id}/close`: Close accumulation.
- `DELETE /accumulation/{id}`: Delete an accumulation by ID.
  - Request Body for POST & PUT:
    ```json
    {
      "name": 'example_name',
      "comment": "Example accumulation",
      "goalSum": 100,
      "endDate": "2025-01-01 00:00:00"
    }
    ```

### Financial Arrangements
- `GET /arrangement`: Retrieve all financial arrangements.
- `GET /arrangement/{id}`: Retrieve a specific financial arrangement by ID.
- `POST /arrangement`: Create a new financial arrangement.
- `PUT /arrangement/{id}`: Update an existing financial arrangement.
- `PUT /transaction/{id}/payment`: Credit the payment.
- `DELETE /arrangement/{id}`: Delete a financial arrangement by ID.
  - Request Body for POST & PUT:
    ```json
    {
      "name": 'example_name',
      "percent": 10,
      "startSum": 10000,
      "endDate": "2025-01-01 00:00:00",
      "fromToUserFunds": true,
      "state": "CREDIT"
    }
    ```

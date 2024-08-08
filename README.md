

# E-Commerce Application

Welcome to my E-Commerce Application! It will allow you to manage your database operations
## Features

- **Customer Management**: Add, update, retrieve, and delete customer records.
- **Order Management**: Add, update, retrieve, and delete order records.
- **Error Handling**: Proper error messages and status codes for different scenarios.
- **Validation**: Input validation using Marshmallow.

## Installation

### Prerequisites

- Python 3.x
- MySQL database
- `pip` for Python package management

### Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/EngineerStephen/e-commerce-app.git
   cd e-commerce-app
   ```

2. **Create a Virtual Environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Required Packages**

   ```bash
   pip install -r requirements.txt
   ```

   Ensure `requirements.txt` includes the following packages:

   ```
   Flask==2.0.3
   Flask-Marshmallow==1.1.1
   marshmallow==3.14.1
   mysql-connector-python==8.0.29
   ```

4. **Configure Database Connection**

   Ensure you have a `connection.py` file with a `connect_db` function that establishes a connection to your MySQL database. 

5. **Run the Application**

   ```bash
   python app.py
   ```

   The application will start and be available at `http://127.0.0.1:5000`.

## API Endpoints

### Customer Endpoints

- **GET /customers**

  Retrieve a list of all customers.

- **POST /customers**

  Add a new customer. Requires JSON payload with `name`, `email`, and `phone`.

- **PUT /customers/<int:id>**

  Update an existing customer identified by `id`. Requires JSON payload with `name`, `email`, and `phone`.

- **DELETE /customers/<int:id>**

  Delete a customer identified by `id`. Will return an error if the customer has associated orders.

### Order Endpoints

- **GET /orders**

  Retrieve a list of all orders.

- **POST /orders**

  Add a new order. Requires JSON payload with `date` and `customer_id`.

- **PUT /orders/<int:order_id>**

  Update an existing order identified by `order_id`. Requires JSON payload with `date` and `customer_id`.

- **DELETE /orders/<int:order_id>**

  Delete an order identified by `order_id`.

## Error Handling

- **400 Bad Request**: Invalid data or request format.
- **404 Not Found**: Resource not found.
- **403 Forbidden**: Action not permitted (e.g., deleting a customer with associated orders).
- **500 Internal Server Error**: Database or server errors.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Create a new Pull Request.

## License

All rights reserved


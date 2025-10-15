# User Wallet Top-Up Logic

The user wallet top-up (deposit) process is a well-defined workflow that involves several controllers and models. The core logic is centralized in the `Gateway/PaymentController.php` file, which orchestrates the process and interacts with various payment gateway-specific controllers.

## 1. Initiation

A user initiates a deposit through one of the following methods:

-   **Web Interface**: The `User/UserController.php`'s `depositHistory` method displays the deposit history and likely links to a deposit form.
-   **API**: The `Api/PaymentController.php`'s `depositInsert` method handles deposit requests from API clients.

## 2. Gateway Selection

The user selects a payment gateway from a list of available options. The application supports a wide range of gateways, including Stripe, Paypal, Coinbase, and more.

## 3. Processing

The `Gateway/PaymentController.php`'s `depositInsert` method is the central point for handling new deposits. It performs the following actions:

1.  **Validates the request**: It checks the deposit amount against the defined limits.
2.  **Creates a `Deposit` record**: It creates a new record in the `deposits` table with the status set to "pending".
3.  **Redirects to the gateway**: It redirects the user to the appropriate gateway-specific `ProcessController` to handle the payment.

## 4. Gateway-Specific Logic

Each payment gateway has its own dedicated `ProcessController.php` located in a subdirectory within the `Gateway` directory (e.g., `Gateway/StripeV3/ProcessController.php`). These controllers are responsible for:

-   **Interacting with the gateway's API**: They send the payment details to the gateway and handle the response.
-   **Updating the `Deposit` record**: They update the `Deposit` record with the transaction details from the gateway.

## 5. Confirmation

Once the payment is successfully processed by the gateway, the gateway's `ProcessController` calls the `userDataUpdate` method in `Gateway/PaymentController.php`.

## 6. Updating User Data

The `userDataUpdate` method is the final step in the deposit process. It performs the following actions:

1.  **Updates the `Deposit` status**: It marks the `Deposit` record as "successful".
2.  **Updates the user's balance**: It creates a new `Transaction` record to reflect the deposit, which implicitly updates the user's wallet balance.
3.  **Sends notifications**: It sends notifications to the user and the admin about the successful deposit.

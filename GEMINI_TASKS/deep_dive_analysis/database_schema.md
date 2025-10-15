# Database Schema

Based on the model names found in `app/Models`, here is an inferred database schema and an explanation of each table's purpose.

## Core Tables

-   **`users`**: Stores user information, including authentication details, profile information, and KYC status.
-   **`deposits`**: Records all deposit transactions made by users.
-   **`withdrawals`**: Records all withdrawal requests made by users.
-   **`transactions`**: A central log of all financial transactions, including deposits, withdrawals, and exchanges.
-   **`exchanges`**: Logs all currency exchange transactions.
-   **`currencies`**: Stores information about the supported currencies.
-   **`gateways`**: Stores information about the payment gateways (e.g., Stripe, Paypal).
-   **`gateway_currencies`**: Maps the supported currencies to the available payment gateways.

## User-Related Tables

-   **`beneficiaries`**: Stores information about the beneficiaries that users can send money to.
-   **`beneficiary_wallets`**: Stores the wallet information for each beneficiary.
-   **`user_logins`**: Logs user login activity for security purposes.
-   **`password_resets`**: Stores password reset tokens.
-   **`admin_password_resets`**: Stores password reset tokens for admins.

## Admin & System Tables

-   **`admins`**: Stores information about the administrators of the platform.
-   **`admin_notifications`**: A log of notifications sent to administrators.
-   **`admin_permissions`**: Defines the permissions for different admin roles.
-   **`general_settings`**: Stores general configuration settings for the application.
-   **`extensions`**: Manages the installed extensions or modules.
-   **`languages`**: Stores the supported languages for the application.
-   **`notification_templates`**: Stores templates for email and SMS notifications.
-   **`notification_logs`**: A log of all notifications sent to users.
-   **`pages`**: Stores the content for static pages (e.g., about us, contact).
-   **`frontends`**: Manages the content of the frontend pages.

## Support & Other Tables

-   **`support_tickets`**: Stores support tickets submitted by users.
-   **`support_messages`**: Stores the messages exchanged within a support ticket.
-   **`support_attachments`**: Stores the files attached to support tickets.
-   **`promo_codes`**: Stores promotional codes that users can apply.
-   **`promo_code_usages`**: Logs the usage of promotional codes.
-   **`refferals`**: Manages the user referral program.
-   **`subscribers`**: Stores the email addresses of users who have subscribed to the newsletter.
-   **`whatsapp_logs`**: Logs the messages sent via WhatsApp.
-   **`blacklist`**: Stores a list of blacklisted users or IP addresses.
-   **`commission_logs`**: Logs the commissions earned through the platform.
-   **`alert_kyc_or_guide_logs`**: Logs alerts related to KYC or user guides.
-   **`account_types`**: Defines different types of user accounts.
-   **`forms`**: A generic form builder.
-   **`generates`**: (Purpose unclear from the name).
-   **`gateway_ipns`**: Logs Instant Payment Notifications from gateways.
-   **`quick_sends`**: (Purpose unclear from the name).

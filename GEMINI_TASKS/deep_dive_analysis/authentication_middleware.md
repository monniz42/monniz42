# Authentication Middleware

The application uses a combination of Laravel's built-in authentication and JWT for securing different parts of the application. The main authentication middleware is implemented in the following files:

## 1. `app/Http/Middleware/Authenticate.php`

-   **Alias**: `auth`
-   **Purpose**: This is the standard authentication middleware for the web interface. It extends Laravel's `Authenticate` class and redirects unauthenticated users to the `user.login` route. It is used to protect routes that require a user to be logged in via the web session.

## 2. `app/Http/Middleware/AuthenticateApi.php`

-   **Alias**: `auth.api`
-   **Purpose**: This middleware is used to protect the API routes. It also extends Laravel's `Authenticate` class but is configured to return a JSON response with a `401 Unauthorized` status code if the user is not authenticated. It is likely used with Laravel Sanctum for token-based authentication.

## 3. `app/Http/Middleware/JwtMiddleware.php`

-   **Alias**: `jwt.verify`
-   **Purpose**: This middleware is specifically for handling JSON Web Token (JWT) authentication. It uses the `tymon/jwt-auth` library to parse and authenticate the JWT from the request. If the token is invalid, expired, or not found, it returns a JSON response with the appropriate error message and a `401 Unauthorized` status code. This middleware is used to protect routes that require a valid JWT, which is common for mobile APIs and single-page applications.

## Other Notable Middleware

-   **`RedirectIfAuthenticated.php`**: This middleware redirects authenticated users away from pages like the login and register pages.
-   **`RedirectIfNotAdmin.php`**: This middleware protects the admin panel by ensuring that only authenticated admin users can access it.
-   **`KycMiddleware.php`**: This middleware restricts access to certain features based on the user's KYC (Know Your Customer) status.

# API & Data Flow

The application exposes a comprehensive set of APIs for both web and mobile clients.

- **Web API**: The `routes/api.php` file defines the API endpoints for the web application. These endpoints handle user authentication, data retrieval, and other actions.
- **Mobile API**: The `app/Http/Controllers/Mobile` directory contains a versioned API for mobile clients, suggesting a dedicated mobile application.
- **Data Flow**: The data flow follows a typical pattern: the request is received by the route, which dispatches it to the controller. The controller interacts with the models to retrieve or persist data and then returns a response, either as a view (for web requests) or as JSON (for API requests).

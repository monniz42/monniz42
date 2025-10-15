# Backend Logic Flow

The backend logic follows the standard MVC pattern of the Laravel framework.

- **Routes**: Defined in `routes/web.php` and `routes/api.php`, they map incoming requests to the appropriate controllers.
- **Middleware**: Used for handling authentication, authorization, and other request filtering.
- **Controllers**: Located in `app/Http/Controllers`, they handle the business logic of the application. The controllers are well-organized into subdirectories based on their functionality (Admin, Api, User, Gateway, Mobile).
- **Models**: (Not explicitly explored, but assumed to be in `app/Models`) They represent the database tables and handle the data persistence.
- **Services**: (Not explicitly explored, but likely used for encapsulating business logic).

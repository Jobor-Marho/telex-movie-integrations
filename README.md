# MovieTrend Integration for Telex

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![Django](https://img.shields.io/badge/django-3.2%2B-green)

A Django-based integration that fetches weekly trending movies from TMDb and displays them in a Telex channel.

## Overview

MovieTrend fetches trending movies from TMDb, formats the data with titles, ratings, overviews, and poster images, and sends it to Telex for display in a designated channel. Perfect for keeping communities updated on popular films.

## Features

- **Weekly Updates**: Automatically fetches trending movies weekly.
- **Rich Media Support**: Includes movie titles, ratings, overviews, and poster images.
- **Telex Integration**: Seamlessly sends formatted data to Telex channels.
- **Customizable**: Configure the number of movies to display via integration settings.
- **Customizable**: Customize the language to receive movies data in.

## Project Structure

```plaintext
movie_trend/
    ├── movieTrendApp/
        ├── tests/                # Test cases for the integration
        ├── static/
            ├── logo/
                ├── logo.png      # movie_trendapp integration logo
        ├── integrations.json    # Telex integration configuration
    ├── manage.py                 # Django management script
    ├── requirements.txt          # Project dependencies
```

## Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/telex_integrations/movie_trend.git
   cd movie_trend
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the development server**:
   ```bash
   python manage.py runserver
   ```

## Usage

### Integration with Telex
1. Provide Telex with the integration JSON URL:
   ```
   http://<your-server-domain>/integration.json
   ```
   Replace `<your-server-domain>` with your server's domain/IP and port (e.g., `localhost:8000`).

2. Telex will periodically fetch trending movies via the `/tick/` endpoint:
   ```
   http://<your-server-domain>/tick/
   ```

### Configuration
- Adjust the number of movies fetched in the Telex integration settings.
- Select language preference you want to receive the movies with.

## Testing

Run the test suite with:
```bash
python manage.py test
```

## Deployment

1. **Production Server Setup**:
   - Use **Gunicorn** as the application server and **Nginx** as the reverse proxy.
   - Example Gunicorn command:
     ```bash
     gunicorn --workers 3 your_project_name.wsgi:application
     ```

2. **Ensure Accessibility**:
   - Verify the `/tick/` endpoint is publicly accessible to Telex servers.

## Screenshots

*(Include screenshots of the integration in a Telex channel here)*
> Example:
><img width="1440" alt="Screenshot 2025-02-18 at 17 31 45" src="https://github.com/user-attachments/assets/1cbac042-e209-41d2-87d8-93bd51d7ded7" />

<img width="1440" alt="Screenshot 2025-02-18 at 17 32 02" src="https://github.com/user-attachments/assets/5f793023-78a0-4f17-9b70-9e60c587b411" />

---

## Contributing
Pull requests are welcome! For major changes, open an issue first to discuss proposed changes.

## License
[MIT](https://choosealicense.com/licenses/mit/) (Add a `LICENSE` file to specify)
```


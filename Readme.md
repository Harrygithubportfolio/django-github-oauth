Github_OAuth
A Django project integrating GitHub OAuth authentication to allow users to sign in using their GitHub accounts.

Features
User authentication via GitHub OAuth.
Ability to sign in to your app using GitHub credentials.
Django Admin integration for managing users and other site data.
Prerequisites
Before running this project, you will need:

Python 3.x
Django 3.x or higher
GitHub OAuth credentials
Installation
Clone this repository:

bash
Copy code
git clone https://github.com/Harrygithubportfolio/django-github-oauth.git
cd django-github-oauth
Create and activate a virtual environment:

bash
Copy code
python3 -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate  # On Windows
Install the dependencies:

bash
Copy code
pip install -r requirements.txt
Set up your GitHub OAuth application:

Go to GitHub OAuth Apps.
Create a new OAuth App.
Set the Authorization callback URL to http://127.0.0.1:8000/accounts/github/login/callback/.
Copy the Client ID and Client Secret provided.
Add the GitHub OAuth credentials to your settings.py:

python
Copy code
AUTHENTICATION_BACKENDS = (
    'social_core.backends.github.GithubOAuth2',
    'django.contrib.auth.backends.ModelBackend',
)

SOCIAL_AUTH_GITHUB_KEY = 'your-client-id'
SOCIAL_AUTH_GITHUB_SECRET = 'your-client-secret'
Run migrations:

bash
Copy code
python3 manage.py migrate
Create a superuser for accessing Django Admin:

bash
Copy code
python3 manage.py createsuperuser
Run the development server:

bash
Copy code
python3 manage.py runserver
Open your browser and go to http://127.0.0.1:8000.

Navigate to /accounts/github/login/ to log in with GitHub.
Usage
Users can log in with their GitHub credentials and access your application.
You can manage users and other models from Django Admin at http://127.0.0.1:8000/admin.
Contributing
Feel free to fork this project and submit pull requests. If you find any bugs or want to improve the functionality, please open an issue and submit a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.
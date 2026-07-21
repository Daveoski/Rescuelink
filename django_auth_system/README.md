# Django Authentication System

A simple Django app with register, login, and logout functionality using Django's built-in auth system.

## Setup

1. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run migrations:
   ```bash
   python manage.py migrate
   ```

4. (Optional) Create a superuser to access /admin:
   ```bash
   python manage.py createsuperuser
   ```

5. Run the development server:
   ```bash
   python manage.py runserver
   ```

6. Visit:
   - `/register/` — create an account
   - `/login/` — log in
   - `/` — home page (requires login)
   - `/logout/` — log out (POST via button on home page)

## Project Structure

```
config/            # Project settings, urls
accounts/          # App with auth views, forms, templates
  ├── forms.py      # RegisterForm
  ├── views.py       # register_view, CustomLoginView, logout_view, home_view
  ├── urls.py         # accounts routes
  └── templates/accounts/  # register.html, login.html, home.html
```

## Git Workflow: Branch → Push → Pull Request

1. **Update main:**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Create a new branch:**
   ```bash
   git checkout -b feature/auth-system
   ```

3. **Stage and commit changes:**
   ```bash
   git add .
   git commit -m "Add register, login, logout functionality"
   ```

4. **Push the branch:**
   ```bash
   git push -u origin feature/auth-system
   ```

5. **Create a Pull Request:**
   - Via GitHub CLI:
     ```bash
     gh pr create --base main --head feature/auth-system --title "Add authentication system" --body "Implements register, login, and logout using Django's built-in auth."
     ```
   - Or via browser: go to your repo → click "Compare & pull request" → set base to `main` → create PR.

6. **After merge, clean up:**
   ```bash
   git checkout main
   git pull origin main
   git branch -d feature/auth-system 
   ```
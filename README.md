# Django Web Framework on Ubuntu

### Global Install from Packages

```
Update local package index with apt:
sudo apt update

Check Python version:
python3 -V

Install Django:
sudo apt install python3-django

Test Django:
django-admin --version
```

### Install with pip in a Virtual Environment

```
Install pip and venv:
sudo apt install python3-pip python3-venv

Create a project directory:
mkdir ~/newproject
cd ~/newproject

Init virtual environment:
python3 -m venv my_env
source my_env/bin/activate

Install Django in my_env:
pip install django

Disable or Re-enable my_env:
deactivate
source my_env/bin/activate
```

## Create a sample project
Place the management script and inner directory in the current directory (with dot):
```
django-admin startproject djangoproject .
```

Migrate the database (SQLite by default):
```
python manage.py migrate
```

### Create an admin user
Enter username, email, and password for the user.

```
python manage.py createsuperuser
```

### Test the Dev Server

Modify `ALLOWED_HOSTS` to add a server IP on `~/djangoproject/settings.py`
```
ALLOWED_HOSTS = ['127.0.0.1']
```

Assign port `8001`
```
sudo ufw allow 8001
```

Start the dev server
```
python manage.py runserver 127.0.0.1:8001
```

Access the login screen with `/admin/`
```
http://127.0.0.1:8001/admin/
```

## Add ons
### Look at open ports on current machine

Install and run `netstat`
```
sudo apt install net-tools

sudo netstat -ntlp
```

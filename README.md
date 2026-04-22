#  Django E-Commerce Project

Un projet web développé avec le framework **Django** dans le cadre du module *Développement Web avec Python* à l'**École Mohammadia d'Ingénieurs**.

---

## Description

Ce projet est une application e-commerce simple permettant de gérer des **produits** et des **catégories**. Il a été réalisé en deux ateliers :

- **Atelier 1** : Découverte de Django, architecture MVT, création du projet et des vues statiques.
- **Atelier 2** : Gestion des données avec l'ORM Django, modèles, migrations, interface admin et connexion MySQL.

---

## Fonctionnalités

- Liste de tous les produits
- Détail d'un produit
- Liste de toutes les catégories
- Détail d'une catégorie avec ses produits
- Interface d'administration Django
- Upload d'images produits
- Connexion à MySQL (ou SQLite par défaut)

---

## Technologies utilisées

| Technologie | Version |
|---|---|
| Python | 3.10+ |
| Django | 4.2 (LTS) |
| MySQL | Via XAMPP (MariaDB 10.4) |
| Pillow | 12.x |

---

## Structure du projet

```
ecommerce_project/
├── ecommerce/              # Dossier principal du projet
│   ├── ecommerce/          # Configuration Django
│   │   ├── settings.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   ├── products/           # Application products
│   │   ├── migrations/
│   │   ├── templates/
│   │   │   └── products/
│   │   │       ├── product_list.html
│   │   │       ├── product_detail.html
│   │   │       ├── category_list.html
│   │   │       └── category_detail.html
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   └── admin.py
│   ├── images/             # Dossier des médias (images produits)
│   │   └── products/
│   └── manage.py
└── myenv/                  # Environnement virtuel (non versionné)
```

---

## Installation et lancement

### 1. Cloner le projet

```bash
git clone https://github.com/votre-username/ecommerce-django.git
cd ecommerce-django
```

### 2. Créer et activer l'environnement virtuel

```bash
# Windows
virtualenv myenv
myenv\scripts\activate

# Linux / macOS
virtualenv myenv
source myenv/bin/activate
```

### 3. Installer les dépendances

```bash
pip install django==4.2
pip install pillow
```

### 4. Configurer la base de données

**Option A — SQLite (par défaut, aucune configuration)**

Django utilise SQLite automatiquement. Aucune configuration supplémentaire n'est nécessaire.

**Option B — MySQL avec XAMPP**

1. Lancer XAMPP et démarrer Apache + MySQL
2. Créer la base `db_ecommerce` dans phpMyAdmin
3. Installer le connecteur :
```bash
pip install mysqlclient
```
4. Modifier `settings.py` :
```python
DATABASES = {
    'default': {
        'ENGINE'  : 'django.db.backends.mysql',
        'NAME'    : 'db_ecommerce',
        'USER'    : 'root',
        'PASSWORD': '',
        'HOST'    : 'localhost',
        'PORT'    : '3306',
    }
}
```

### 5. Appliquer les migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Créer un super-utilisateur (admin)

```bash
python manage.py createsuperuser
```

### 7. Lancer le serveur

```bash
python manage.py runserver
```

---

## URLs disponibles

| URL | Description |
|---|---|
| `http://127.0.0.1:8000/products/` | Liste des produits |
| `http://127.0.0.1:8000/products/<id>` | Détail d'un produit |
| `http://127.0.0.1:8000/products/categories/` | Liste des catégories |
| `http://127.0.0.1:8000/products/category/<id>/` | Produits d'une catégorie |
| `http://127.0.0.1:8000/admin/` | Interface d'administration |

---

## 👤 Auteur

**Nada Chahbane**
École Mohammadia d'Ingénieurs — Rabat
Année universitaire 2025–2026
Encadré par : Mr. A. Bousselham

---

## 📄 Licence

Projet académique — École Mohammadia d'Ingénieurs

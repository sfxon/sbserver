# Scoreboard Server

Diese Anwendung stellt die Server-Anwendung für unsere Scoreboards dar.

## Current Features

None

## Upcoming Features

* **User Management** mit Login, Logout, Registration, Password reset, Account management (crud).

* **Raum Management** - jeder Raum ist ein Scoreboard für eine Spiel-Instanz, gemanaged durch einen Benutzer.

* Websocket integration für **Spiel-Leiter** und weitere Anwendungen, wie bspw. sensorgesteuerte Anwendungen, welche Spieldaten über Sensoren aktualisieren.

* Websocket integration für **Anzeige-Clients**. Ermöglicht es bspw. über mehrere verteilte Mini-PCs und ein Netzwerk mehrere Monitore/Großraumdisplays übers Netzwerk in Echtzeit zu aktualisieren.

* Simplere API Integration, für Umgebungen, bei denen das reine Speichern der Daten genügt, ohne dass die komplexere Websocket Technologie dazu verwendet werden muss.

* Langzeit-Speicher aller Events in einem Raum.

* Flexible Raum und Spieldaten, durch ein JSON gesteuertes Protokoll. Flexible Anzeige/Designs, angepasst auf das jeweilige Spiel.

* Rendering und Erstellung von sfxon/scoreboard als Frontend Anwendung, unabhängig vom restlichen System, managebar über lokalen Speicher, für Minimalanwendungen.

## System requirements

1. PHP 8.4

2. Composer / nodejs

3. MySQL 8


## Installation

1. Alle Dateien auf den Server kopieren.

2. ```composer install```

3. .env Datei bearbeiten<br>You can use a copy of .env.example. At least you should set APP_NAME and setup a mysql connection.

4. Import database or run migration<br>
```php artisan migrate```<br>
oder, falls es Probleme gibt:<br>
```php artisan migrate:fresh```

## Verwendete Technologien

* **Laravel** als Server/Backend System, User Management und Langzeit-Datenbank-Speichersystem mit API.

* **Reverb** als Websocket Server

* **Javascript Websocket Client** der im Browser läuft.

* Ein **Python Websocket Client** für Sensoren ist als separates Projekt verfügbar.

* **Dockware** als Entwicklungsumgebung. Eine docker-compose.yml Datei liegt als Beispiel bei.

## Umsetzungs-Dokumentation

```bash
# Create laravel project and additional needed resources.
composer create-project laravel/laravel sbserve
cd sbserver
composer require laravel/reverb
php artisan reverb:install --no-interaction
npm install
npm install laravel-echo pusher-js

# Configure database, set APP_NAME and MySQL connection.
nano .env

# Start migration
npm artisan migrate:fresh
```
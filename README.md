# SQL simplement

> Guide pratique et pédagogique pour apprendre et comprendre SQL sans se perdre dans une documentation indigeste.

**SQL simplement** est un guide SQL complet destiné aux débutants comme aux développeurs souhaitant consolider leurs bases.

L'objectif n'est pas de mémoriser une multitude de requêtes, mais de comprendre la logique permettant de **lire, filtrer, relier, modifier, structurer et sécuriser des données**.

---

## 📚 Contenu du guide

Le guide est organisé en 14 grandes parties :

1. **Comprendre SQL**
   - DQL, DML, DDL et TCL
   - Fonctionnement d'une base relationnelle
   - Structure d'une table

2. **PHP : connexion aux bases de données**
   - PDO
   - Connexion MySQL
   - Connexion SQLite
   - Organisation d'une base SQLite

3. **PHP : exécuter des requêtes SQL**
   - `exec()`
   - `query()`
   - `prepare()`
   - Récupération des résultats

4. **PHP : sécurité**
   - Requêtes préparées
   - `bindValue()`
   - `execute()`
   - Paramètres nommés
   - Prévention des injections SQL

5. **SELECT**
   - Sélection de colonnes
   - `WHERE`
   - `AND`, `OR`, `NOT`
   - `LIKE`
   - `IN`
   - `BETWEEN`
   - `NULL`
   - `DISTINCT`
   - `ORDER BY`
   - `LIMIT`
   - `OFFSET`
   - `CASE`

6. **INSERT / UPDATE / DELETE**
   - Insertion simple
   - Insertions multiples
   - `INSERT ... SELECT`
   - Modification de données
   - Suppression
   - UPSERT

7. **JOIN**
   - `INNER JOIN`
   - `LEFT JOIN`
   - `RIGHT JOIN`
   - `FULL OUTER JOIN`
   - `SELF JOIN`

8. **Agrégation**
   - `COUNT()`
   - `SUM()`
   - `AVG()`
   - `MIN()`
   - `MAX()`
   - `GROUP BY`
   - `HAVING`

9. **Structure des bases**
   - `CREATE DATABASE`
   - `CREATE TABLE`
   - `ALTER TABLE`
   - `DROP`
   - `TRUNCATE`
   - `DELETE`

10. **Contraintes**
    - `PRIMARY KEY`
    - `FOREIGN KEY`
    - `NOT NULL`
    - `UNIQUE`
    - `DEFAULT`
    - `CHECK`

11. **Performance**
    - Index
    - Index uniques
    - `VIEW`
    - `EXPLAIN`

12. **Transactions**
    - `BEGIN`
    - `COMMIT`
    - `ROLLBACK`

13. **SQL avancé**
    - Sous-requêtes
    - `EXISTS`
    - CTE
    - `WITH`
    - `UNION`
    - `UNION ALL`
    - CTE récursives
    - Fonctions fenêtre
    - `ROW_NUMBER()`
    - `RANK()`

14. **Fonctions SQL utiles**
    - `COUNT()`
    - `SUM()`
    - `AVG()`
    - `MIN()`
    - `MAX()`
    - `LOWER()`
    - `UPPER()`
    - `LENGTH()`
    - `COALESCE()`
    - `ROUND()`

---

## 🗄️ Bases de données abordées

Le guide présente le SQL standard ainsi que les variantes courantes utilisées avec :

- MySQL
- MariaDB
- PostgreSQL
- SQLite
- SQL Server

Lorsque la syntaxe dépend du moteur SQL, le guide le signale et présente les différences lorsqu'elles sont importantes.

---

## 🐘 PHP + PDO

Une partie importante du guide est consacrée à l'utilisation de SQL avec PHP via **PDO**.

Exemple de connexion MySQL :

```php
$pdo = new PDO(
    'mysql:host=localhost;dbname=ma_base;charset=utf8mb4',
    'mon_utilisateur',
    'mon_mot_de_passe'
);
```

Exemple avec SQLite :

```php
$pdo = new PDO(
    'sqlite:' . __DIR__ . '/db.sqlite'
);
```

Le guide explique également les principales méthodes PDO :

```php
$pdo->exec($sql);
$pdo->query($sql);
$pdo->prepare($sql);
```

---

## 🔐 Sécurité SQL

Le guide insiste sur l'utilisation des **requêtes préparées** lorsqu'une valeur provient d'un utilisateur.

Exemple :

```php
$sql = "SELECT * FROM clients WHERE id = :id";

$stmt = $pdo->prepare($sql);

$stmt->execute([
    'id' => 5
]);
```

La concaténation directe de données utilisateur dans une requête SQL est déconseillée.

Le guide présente également la différence entre `bindValue()` et `execute()`, notamment lorsqu'il est nécessaire de contrôler explicitement le type d'un paramètre.

---

## ✨ Caractéristiques

- 📖 Explications accessibles
- 💻 Exemples SQL directement utilisables
- 🐘 Exemples PHP avec PDO
- 🔐 Notions de sécurité
- 🗄️ MySQL, MariaDB, PostgreSQL, SQLite et SQL Server
- 🔗 Requêtes avec plusieurs tables
- ⚡ Notions de performance
- 🔄 Transactions
- 🧠 SQL avancé
- 📱 Interface responsive
- 🌙 Mode clair / sombre
- 🧭 Sommaire avec navigation par sections

Le guide utilise notamment Tailwind CSS pour son interface et propose un changement de thème conservé dans `localStorage`. 
---

## 🚀 Utilisation

Le projet est volontairement simple : il s'agit d'une page HTML autonome.

Il suffit de télécharger ou cloner le projet puis d'ouvrir le fichier HTML dans un navigateur.

```bash
git clone https://github.com/USERNAME/sql-simplement.git
cd sql-simplement
```

Puis ouvrir :

```text
guide-sql-complet-PHP-MySQL-SQLite-dark-fix.html
```

Aucun serveur PHP n'est nécessaire pour consulter le guide.

---

## 🎯 Pour qui ?

Ce guide s'adresse notamment :

- aux personnes qui débutent avec SQL ;
- aux développeurs PHP souhaitant mieux maîtriser PDO ;
- aux personnes découvrant MySQL ou SQLite ;
- aux développeurs souhaitant revoir les fondamentaux ;
- aux étudiants et autodidactes ;
- à toute personne souhaitant avoir une référence SQL pratique sous la main.

---

## ⚠️ À propos du SQL

SQL possède plusieurs dialectes et toutes les commandes ne sont pas identiques selon le moteur utilisé.

Ce guide ne prétend donc pas contenir littéralement toutes les requêtes SQL imaginables. Il rassemble plutôt un socle large de connaissances utiles, des fondamentaux jusqu'à des notions avancées.

---

## 📁 Structure

```text
.
└── guide-sql-complet-PHP-MySQL-SQLite-dark-fix.html
```

Le guide fonctionne directement dans un navigateur et ne nécessite pas de framework ou de système de build.

---

## 🛠️ Technologies

- HTML5
- CSS3
- JavaScript
- Tailwind CSS
- SQL
- PHP / PDO

---

## 📄 Licence

Ajoutez ici la licence de votre choix si vous souhaitez distribuer le projet sous une licence open source.

---

## 💡 Philosophie

> **Comprendre avant de copier.**

SQL est un langage immense. L'objectif de ce guide est de donner suffisamment de compréhension pour pouvoir ensuite apprendre facilement les spécificités de chaque moteur SQL.

**Lire → filtrer → relier → modifier → structurer → sécuriser.**

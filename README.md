## Créer un projet Laravel 
composer create-project --prefer-dist laravel/laravel udemytraining

## Accéder directement au dossier de l'application créée 
code .

## Lancer le serveur avec l'application 
php artisan serve

## Créer un contrôleur (contrôleur vide)
php artisan make::controller MyController

## Créer un contrôleur avec traitements (GET, POST, PUT/PATCH, DELETE)
php artisan make:controller -r ArticleController

## Fichier de migration 
php artisan make:migration create_post_table

## Créer un modèle 
php artisan make:model Article

## Créer les tables 
php artisan migrate

## Annuler la création des tables
php artisan migrate:rollback

## Nettoyer la config de Laravel
php artisan config clear

## Nettoyer le cache 
php artisan cache:clear

## Annuler la migration 
php artisan migrate:reset

## Créer un seeder
php artisan make:seed ArticleSeeder

## Appeler le database seeder
php artisan db:seed

#####################################################################

## Exécuter directement du code PHP (shell -> exit pour quitter)
php artisan tinker

## Récupérer toutes les catégories 
App\Category::all();

## Récupérer une catégorie aléatoire
App\Category::all()->random(1)->first->id;

#####################################################################

## Middleware 
Un Middleware va fournir un mécanisme pratique pour filtrer les requêtes HTTP qui vont entrer dans l'application.

middleware autth(voir si l'utilisateur est authentifié)

## Créer un modèle et gérer la migration associée à ce modèle 
php artisan make:model Course -m

## Les relations entre modèles

## One to One 
Relation la plus simple : un modèle qui appartient et fait référence à un autre modèle 

## One to Many 
Relation plus complexe, fait intervenir plus d'éléments (un post sera lié à plusieurs commentaires : entre 0 et plusieurs commentaire et 1 commentaire va appartenir à un seul post, la relation est différente dans les deux sens : un commentaire appartient à un seul post et un post peut avoir entre 0 et plusieurs commentaires, on aura un post_id dans la table "Comment", à partir du commentaire, on pourra directement retrouver le post grâce au post_id, plusieurs commentaires pourront avoir le même post_id).

## Many to Many 
La plus complexe : elle va nécessiter une table de relation entre les deux modèles concernés par la relation (un utilisateur peut avoir plusieurs rôles, on ne sait pas préciser ni dans rôle, ni dans user, le user_id directement, il ne fera référence qu'à un seul user. On aura donc une table role user qui fera la relation entre les deux modèles User et Role et qui va contenir pour chaque user_id, le rôle en question, cette table ne contiendra que des id pour faciliter la mise en place de la relation). Laravel propose, grâce à ses relations, de mettre en place des propriétés pour récupérer un modèle depuis un autre modèle.

## Faire un lien entre "storage" et "app/public" (connecter les deux dossiers)
## Résolution du souics : https://www.it-swarm.dev/fr/php/stockage-dans-laravel-dit-lien-symbolique-aucun-fichier-de-ce-type/835197221/
php artisan storage:link 

## Installation du package pour récupérer les informations de la vidéo 
composer require james-heinrich/getid3

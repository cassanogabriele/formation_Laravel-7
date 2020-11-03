## Apprentissage 

## Créer un projet Laravel 

``` composer create-project --prefer-dist laravel/laravel udemytraining ```

## Accéder directement au dossier de l'application créée 

code .

## Lancer le serveur avec l'application 

``` php artisan serve ```

## Créer un contrôleur (contrôleur vide)

``` php artisan make::controller MyController ```

## Créer un contrôleur avec traitements (GET, POST, PUT/PATCH, DELETE)

``` php artisan make:controller -r ArticleController ```

## Fichier de migration 

``` php artisan make:migration create_post_table ```

## Créer un modèle 

``` php artisan make:model Article ```

## Créer les tables 

``` php artisan migrate ```

## Annuler la création des tables

``` php artisan migrate:rollback ```

## Nettoyer la config de Laravel

``` php artisan config clear ```

## Nettoyer le cache 

``` php artisan cache:clear ```

## Annuler la migration 

``` php artisan migrate:reset ```

## Créer un seeder

``` php artisan make:seed ArticleSeeder ```

## Appeler le database seeder

``` php artisan db:seed ```

## Exécuter directement du code PHP (shell -> exit pour quitter)

``` php artisan tinker ```

## Récupérer toutes les catégories 

``` App\Category::all(); ```

## Récupérer une catégorie aléatoire

``` App\Category::all()->random(1)->first->id; ```

## Middleware 

Un Middleware va fournir un mécanisme pratique pour filtrer les requêtes HTTP qui vont entrer dans l'application.

middleware autth(voir si l'utilisateur est authentifié)

## Créer un modèle et gérer la migration associée à ce modèle 

``` php artisan make:model Course -m ```

## Les relations entre modèles

## One to One 

Relation la plus simple : un modèle qui appartient et fait référence à un autre modèle 

## One to Many 

Relation plus complexe, fait intervenir plus d'éléments (un post sera lié à plusieurs commentaires : entre 0 et plusieurs commentaire et 1 commentaire va appartenir à un seul post, la relation est différente dans les deux sens : un commentaire appartient à un seul post et un post peut avoir entre 0 et plusieurs commentaires, on aura un post_id dans la table "Comment", à partir du commentaire, on pourra directement retrouver le post grâce au post_id, plusieurs commentaires pourront avoir le même post_id).

## Many to Many 

La plus complexe : elle va nécessiter une table de relation entre les deux modèles concernés par la relation (un utilisateur peut avoir plusieurs rôles, on ne sait pas préciser ni dans rôle, ni dans user, le user_id directement, il ne fera référence qu'à un seul user. On aura donc une table role user qui fera la relation entre les deux modèles User et Role et qui va contenir pour chaque user_id, le rôle en question, cette table ne contiendra que des id pour faciliter la mise en place de la relation). Laravel propose, grâce à ses relations, de mettre en place des propriétés pour récupérer un modèle depuis un autre modèle.

## Faire un lien entre "storage" et "app/public" (connecter les deux dossiers)
## Résolution du souciss : https://www.it-swarm.dev/fr/php/stockage-dans-laravel-dit-lien-symbolique-aucun-fichier-de-ce-type/835197221/

``` php artisan storage:link ```

## Installation du package pour récupérer les informations de la vidéo 

``` composer require james-heinrich/getid3 ```

## bundle pour faire un panier

https://github.com/darryldecode/laravelshoppingcart/blob/master/src/Darryldecode/Cart/Cart.php

## Installation et configuration 

https://packagist.org/packages/darryldecode/cart

## Stripe 

https://dashboard.stripe.com/login

cassanogabriele78@gmail.com
Intheclawsofawitch1978

``` composer require stripe/stripe-php ```

Documentation : https://stripe.com/docs/stripe-js
Utilisation : https://github.com/stripe/stripe-php

## API (Application Programming Interface)

Elle va permettre à deux applications de communiquer entre elles : on communiquera depuis l'application Laravel avec Udemy pour récupérer des informations. Une API, expose, rend disponible des fonctionnalités ou des données. Pour pouvoir les utiliser, la plupart des API requièrent une clé (API Key), voir parfois deux. Cette clé va permettre à l'API d'identifier comme étant utilisateur et avoir les droits pour se servir de cet API.

https://www.udemy.com/instructor/account/api/

Aller à "Clients API" et il faut faire une demande de clé en cliquant sur le bouton "Demander un client API affilié".

Email envoyé car pas moyen de créer la clé API pour continuer la formation, le formulaire bloque au champs nom, j'ai beau essayé avec n'importe quoi, rien à faire.

## Fichier word (résumé)

## MVC 

## Les modèles

Données de l’application et permettent l’interaction avec la base de données. Le modèle va gérer la base de données.

## Les vues

Tout ce qui est représentation visuelle : templates, des résultats de la requête que l’utilisateur à effectué. La vue produit les pages HTML.

## Les contrôleurs
Ils vont intercepter les requêtes et c’est ici que se passera tout le traitement des données. Tout le reste se fait dans le contrôleur.
Notion essentielle qu’on utilise tout au long d’une application Laravel, il va s’occuper de rendre la vue.
Le contrôleur permet d’utiliser des fonctions.

Le user sur le navigateur va vouloir accéder à une page, c’est là qu’intervient le routing qui va faire correspondre cette url au bon contrôleur et à la bonne fonction qui va gérer ce rendu. On passe dans le contrôleur, si il y interaction avec la base de données, on va gérer ça avec le modèle, qui va faire l’intermédiaire entre le contrôleur et la base de données, le contrôleur fait le traitement ensuite de tout ce qu’il a récupéré. On va rendre une nouvelle vue, ce que le user va voir au niveau du navigateur : du HTML + un peu de traitement. Laravel intègre un système de routage qui va permettre de créer des urls très simples et naturelles, l’ORM Eloquent qui va permettre de simplifier l’accès à la base de données en travaillant avec des objets plutôt que d’accéder directement à des données relationnelles. Le QueryBuilder permet de construire sa propre requête SQL avec une syntaxe simplifiée tout en manipulant des objets. Blade est le template qui permet de favoriser la lisibilité et la logique du code, il permettra de construire les rendus visuels, principalement du code HTML mais aussi un système d’inclusion de fichiers, d’héritages, de boucles, de conditions, on peut même directement écrire du code PHP. Laravel prend en charge la gestion des cookies et de la session qui sont utilisées pour stocker des informations sur l’utilisateur au fur et à mesure de sa navigation sur le site. Système de validation très performant et très simplement, pour avoir un contrôle total entre les différentes pages et le contrôleur. La validation frontend est tout le JavaScript, côté client (un champ obligatoire dans un formulaire). Laravel propose de la validation backend pour récupérer les données, les traiter, vérifier ce qu’on nous envoie et valider ou non ces données, c’est très performant. Le système de migration pour les bases de données permet de créer et de mettre à jour un schéma de base de données, le but est de centraliser toute la gestion de la base de données au sein de l’application.

## Commandes Laravel

## Créer une application 

``` composer create-project –prefer-dist laravel/laravel training ```

## Voir l’arborescence de l’application

``` code . (dans Visual Studio)  ```

## Lancer l’application

``` php artisan serve ```

## Pour cliquer sur une classe et chercher dans l’architecture pour trouver la classe et l’inclure.

``` CTRL + ALT + I ```

## Quizz 

1. Quelles éléments composent le modèle MVC ? 

Modèle Vue Controleur 

2. Comment afficher une variable dans un fichier blade ? 

``` {{ $variable }} ```

3. Quelle directive permet de protéger son application d'attaque CSRF (cross-site request forgery) ? 

``` @csrf ```

4. Comment récupérer un élément envoyé via un formulaire, grâce à la "$request" ? 

## Exemple 
Méthode d'envoie "POST" et nom de la valeur qu'on souhaite récupérer est "prénom".

``` $request->input('prenom'); ```

5. Quelle méthode permet la modification d'une ressource ? 

``` PUT ```

6. A quel endroit sont stockés les fichiers sur Laravel ? 

``` /storage/app/public ```

7. Quelle méthode permet la suppression d'un modèle ? 

``` $model->delete(); ```

8. Quelle méthode permet de récupérer un modèle selon son id ? 

``` find($id) ```

9. Lors de la suppression d'un modèle, tous les fichiers attachés à ce modèle sont supprimés automatiquement.

FAUX 

## Solution pour problème d'appel à un serveur distant https avec Laravel 

<?php
namespace App\Http\Clients;
use Illuminate\Support\Facades\Http;

class UdemyClient {    
```
public function getUdemyCourses(){
  // On va pouvoir récupérer la logique pour pouvoir récupérer les cours d'Udemy 

  // Vérifier qu'on récupère bien les variables d'environnement 

  // dd(env('UDEMY_CLIENT_ID'), env('UDEMY_CLIENT_SECRET'));

  // S'authentifier auprès d'Udemy
  $client = 
        Http::withOptions([ 
            'verify'     => false, 
            ])->withBasicAuth(env('UDEMY_CLIENT_ID'), env('UDEMY_CLIENT_SECRET'));

        // Construire et récupérer la réponse 
        $response = $client->get('https://www.udemy.com/api-2.0/courses/');
        dd($response);
   }
}
```











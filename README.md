<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[British Software Development](https://www.britishsoftware.co)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- [UserInsights](https://userinsights.com)
- [Fragrantica](https://www.fragrantica.com)
- [SOFTonSOFA](https://softonsofa.com/)
- [User10](https://user10.com)
- [Soumettre.fr](https://soumettre.fr/)
- [CodeBrisk](https://codebrisk.com)
- [1Forge](https://1forge.com)
- [TECPRESSO](https://tecpresso.co.jp/)
- [Runtime Converter](http://runtimeconverter.com/)
- [WebL'Agence](https://weblagence.com/)
- [Invoice Ninja](https://www.invoiceninja.com)
- [iMi digital](https://www.imi-digital.de/)
- [Earthlink](https://www.earthlink.ro/)
- [Steadfast Collective](https://steadfastcollective.com/)
- [We Are The Robots Inc.](https://watr.mx/)
- [Understand.io](https://www.understand.io/)
- [Abdel Elrafa](https://abdelelrafa.com)
- [Hyper Host](https://hyper.host)
- [Appoly](https://www.appoly.co.uk)
- [OP.GG](https://op.gg)
- [云软科技](http://www.yunruan.ltd/)

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Apprentissage 

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
## Résolution du souciss : https://www.it-swarm.dev/fr/php/stockage-dans-laravel-dit-lien-symbolique-aucun-fichier-de-ce-type/835197221/
php artisan storage:link 

## Installation du package pour récupérer les informations de la vidéo 
composer require james-heinrich/getid3

## bundle pour faire un panier
https://github.com/darryldecode/laravelshoppingcart/blob/master/src/Darryldecode/Cart/Cart.php

## Installation et configuration 
https://packagist.org/packages/darryldecode/cart


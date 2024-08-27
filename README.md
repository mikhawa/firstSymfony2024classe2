# firstSymfony

## Installation

  symfony new firstSymfony

Nous voici avec un Symfony vierge.

On change de répertoire

```bash
cd firstSymfony

symfony serve -d
```

### Installation de Maker

Nous allons installer `maker` en mode développement :

```bash
composer require --dev symfony/maker-bundle
```

### Création d'un Controller

```bash
php bin/console make:controller
```

Nous le nommerons `TestController`

Puis nous modifions l'envoie de `json` par défaut :

```php
<?php

namespace App\Controller;

# ce code

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\JsonResponse;
use Symfony\Component\Routing\Attribute\Route;

class TestController extends AbstractController
{
    #[Route('/test', name: 'app_test')]
    public function index(): JsonResponse
    {
        return $this->json([
            'message' => 'Welcome to your new controller!',
            'path' => 'src/Controller/TestController.php',
        ]);
    }
}

# par ce code

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
// use Symfony\Component\HttpFoundation\JsonResponse;
use Symfony\Component\Routing\Attribute\Route;
use Symfony\Component\HttpFoundation\Response;

class TestController extends AbstractController
{
    #[Route('/test', name: 'app_test')]
    public function index(): Response
    {
        return new Response('Hello World');
    }
}

```

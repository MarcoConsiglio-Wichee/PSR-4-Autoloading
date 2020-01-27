# PSR-4-Autoloading
This is a PHP autoloader implementing the standard PSR-4

# PSR-4-Autoloading
This is a PHP autoloader implementing the standard PSR-4.
I found this on [https://www.php-fig.org/psr/psr-4/examples/](https://www.php-fig.org/psr/psr-4/examples/).

## How to use
Place the `Psr4AutoloaderClass.php` file in the direcotory of your choice, for example:

    /Project/vendor/PSR-4/Psr4AutoloaderClass.php
If it suits you, define a constant for the base directory of the project.

    define("BASE_PATH", "/app/www_https/Project");
then require the autoloader file:

    require_once BASE_PATH."/vendor/PSR-4/Psr4AutoloaderClass.php";
Now, you have to register the namespace. You can register more than one namespace, and the same namespace can have multiple different directory. Set the autoloader like this:

    $loader = new \PSR4\Psr4AutoloaderClass;
    $loader->register();
    $loader->addNamespace("CompanyName\Project", BASE_PATH."/src");
    $loader->addNamespace("CompanyName\Project", BASE_PATH."/src/strategies");
    $loader->addNamespace("CompanyName\Project", BASE_PATH."/src/handlers");
 Finally, in the same file, you can use a class as you ever did:

    use CompanyName\Project\Ticket;
    use CompanyName\Project\TicketManager;
    
    // Create a new Ticket.
    $ticket = new CompanyName\Project\Ticket();
Enjoy coding!


> Written with [StackEdit](https://stackedit.io/).
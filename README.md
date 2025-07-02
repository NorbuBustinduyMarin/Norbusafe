Cannot resolve argument $request of "App\Controller\AlbumController::edit()": Cannot determine controller argument for "App\Controller\AlbumController::edit()": the $request argument is type-hinted with the non-existent class or interface: "App\Controller\Request". Did you forget to add a use statement?
Symfony\Component\DependencyInjection\Exception\
RuntimeException
in C:\xampp\htdocs\sd23-p07-symfony-herkanstoets-b2-NorbuBustinduyMarin\vendor\symfony\dependency-injection\Container.php (line 397)
    {        if ('service_container' === $id) {            return $this;        }        if (\is_string($load)) {            throw new RuntimeException($load);        }        if (null === $method) {            return false !== $registry ? $this->{$registry}[$id] ?? null : null;        }        if (false !== $registry) {
    waarom krijg ik deze error help mij alsjeblieft

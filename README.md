Could not load type "App\Controller\AlbumType": class does not exist.
Symfony\Component\Form\Exception\
InvalidArgumentException
in C:\xampp\htdocs\sd23-p07-symfony-herkanstoets-b2-NorbuBustinduyMarin\vendor\symfony\form\FormRegistry.php (line 72)
            }            if (!$type) {                // Support fully-qualified class names                if (!class_exists($name)) {                    throw new InvalidArgumentException(sprintf('Could not load type "%s": class does not exist.', $name));                }                if (!is_subclass_of($name, FormTypeInterface::class)) {                    throw new InvalidArgumentException(sprintf('Could not load type "%s": class does not implement "Symfony\Component\Form\FormTypeInterface".', $name));                }


            di is de volgende melding die ik krijg

App\Controller\AlbumController::showAlbum(): Argument #2 ($id) must be of type int, string given, called in C:\xampp\htdocs\sd23-p07-symfony-herkanstoets-b2-NorbuBustinduyMarin\vendor\symfony\http-kernel\HttpKernel.php on line 181
TypeError
in C:\xampp\htdocs\sd23-p07-symfony-herkanstoets-b2-NorbuBustinduyMarin\src\Controller\AlbumController.php (line 25)
            'albums' => $albums,        ]);    }    #[Route('/album/{id}', name: 'app_show_album')]    public function showAlbum(EntityManagerInterface $entityManager, int $id): Response    {        $album = $entityManager->getRepository(Album::class)->find($id);        return $this->render('album/show-album.html.twig', [            'album' => $album,        ]);
wat moet ik doen ik krijg deze error

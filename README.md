#[Route('/album/new', name: 'app_album_new')]
public function new(Request $request, EntityManagerInterface $entityManager): Response
{
    $album = new Album();
    $form = $this->createForm(AlbumType::class, $album);
    $form->handleRequest($request);

    if ($form->isSubmitted() && $form->isValid()) {
        $entityManager->persist($album);
        $entityManager->flush();

        return $this->redirectToRoute('app_album');
    }

    return $this->render('album/new.html.twig', [
        'form' => $form->createView(),
    ]);
}
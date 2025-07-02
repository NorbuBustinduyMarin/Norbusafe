#[Route('/album/{id}/edit', name: 'app_album_edit')]
public function edit(Request $request, Album $album, EntityManagerInterface $entityManager): Response
{
    $form = $this->createForm(AlbumType::class, $album);
    $form->handleRequest($request);

    if ($form->isSubmitted() && $form->isValid()) {
        $entityManager->flush();

        return $this->redirectToRoute('app_album');
    }

    return $this->render('album/edit.html.twig', [
        'form' => $form->createView(),
        'album' => $album,
    ]);
}

#[Route('/album/{id}/delete', name: 'app_album_delete', methods: ['POST'])]
public function delete(Request $request, Album $album, EntityManagerInterface $entityManager): Response
{
    if ($this->isCsrfTokenValid('delete' . $album->getId(), $request->request->get('_token'))) {
        $entityManager->remove($album);
        $entityManager->flush();
    }

    return $this->redirectToRoute('app_album');
}
<a href="{{ path('app_album_new') }}">➕ Nieuw album toevoegen</a>

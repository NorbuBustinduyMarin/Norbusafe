use App\Repository\ProductRepository;

#[Route('/product', name: 'app_product')]
public function index(ProductRepository $productRepository): Response
{
    $products = $productRepository->findAll();

    return $this->render('product/index.html.twig', [
        'products' => $products,
    ]);
}
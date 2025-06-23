use App\Entity\Product;
use App\Form\ProductType;
use Doctrine\ORM\EntityManagerInterface;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

#[Route('/product', name: 'app_product_')]
class ProductController extends AbstractController
{
    #[Route('/new', name: 'new')]
    public function new(Request $request, EntityManagerInterface $em): Response
    {
        $product = new Product(); // 🆕 leeg product-object

        $form = $this->createForm(ProductType::class, $product); // 🔧 koppel formulier aan dit object
        $form->handleRequest($request); // 📥 kijk of er POST-data is

        if ($form->isSubmitted() && $form->isValid()) {
            $em->persist($product);  // ⏳ opslaan klaarzetten
            $em->flush();            // ✅ echt opslaan in database

            $this->addFlash('success', 'Product toegevoegd!');
            return $this->redirectToRoute('app_product_index'); // 🔁 terug naar lijst
        }

        return $this->render('product/new.html.twig', [ // 🖼️ formulier tonen
            'form' => $form->createView(),
        ]);
    }
}
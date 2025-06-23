Variable "products" does not exist in product/index.html.twig at line 12.
Twig\Error\
RuntimeError
Show exception properties
in C:\xampp\htdocs\sd23-p08-symfony-eindtoets-b2l-NorbuBustinduyMarin\templates\product\index.html.twig (line 12)
        <div class="container">            <h2 class="page-section-heading text-center text-uppercase text-secondary mb-0">Product Overzicht</h2>            <div class="divider-custom"></div>            <div class="row justify-content-center">                {% for product in products %}                    <div class="col-md-4 mb-5">                        <div class="card shadow">                            <img src="https://via.placeholder.com/600x400" class="card-img-top" alt="...">                            <div class="card-body text-center">                                <h5 class="card-title">{{ product.name }}</h5>
        wat moet ik verbeteren dan?

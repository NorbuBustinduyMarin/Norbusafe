 {% extends 'base.html.twig' %}

{% block title %}Product Overzicht{% endblock %}

{% block body %}
<section class="page-section portfolio" id="portfolio">
    <div class="container">
        <h2 class="page-section-heading text-center text-uppercase text-secondary mb-0">Product Overzicht</h2>
        <div class="divider-custom"></div>

        <div class="row justify-content-center">
            {% for product in products %}
                <div class="col-md-4 mb-5">
                    <div class="card shadow">
                        <img src="https://via.placeholder.com/600x400" class="card-img-top" alt="...">
                        <div class="card-body text-center">
                            <h5 class="card-title">{{ product.name }}</h5>
                            <p class="card-text">€ {{ product.price|number_format(2, ',', '.') }}</p>
                        </div>
                    </div>
                </div>
            {% else %}
                <p class="text-center">Geen producten gevonden.</p>
            {% endfor %}
        </div>
    </div>
</section>
{% endblock %}
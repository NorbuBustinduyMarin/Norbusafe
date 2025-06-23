<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta name="description" content="School website van de Heppie Kemper :-)">
    <meta name="author" content="Heppie Kemper">
    <title>{% block title %}Heppie Kemper!{% endblock %}</title>
    {#    Loading the javascript files/ CDN#}
    <script src="https://use.fontawesome.com/releases/v6.3.0/js/all.js" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>

    {# Loading the link/ CSS files and the favicon  #}
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700" rel="stylesheet" type="text/css" />
    <link href="https://fonts.googleapis.com/css?family=Lato:400,700,400italic,700italic" rel="stylesheet" type="text/css" />
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
    {% block stylesheets %}
    {% endblock %}
    {% block javascripts %}
        {% block importmap %}{{ importmap('app') }}{% endblock %}
    {% endblock %}
</head>
<body id="page-top">
    {% include('nav.html.twig') %}
    <header class="masthead bg-primary text-white text-center">
        <div class="container-fluid">
            {%  for label, messages in app.flashes %}
                {%  for msg in messages %}
                    <div class="alert alert-{{ label }}" role="alert">
                        {{ msg }}
                    </div>
                {%  endfor %}
            {%  endfor %}
            {% block body %}{% endblock %}
        </div>
    </header>
</body>
</html>

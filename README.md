{% extends 'base.html.twig' %}

{% block title %}Nieuw Album Toevoegen{% endblock %}

{% block body %}
    <h1>Nieuw Album Toevoegen</h1>

    {{ form_start(form) }}
        {{ form_row(form.naam) }}
        {{ form_row(form.jaar) }}
        {{ form_row(form.artiest) }}
        {{ form_row(form.genre) }}
        
        <button class="btn btn-success">Opslaan</button>
    {{ form_end(form) }}

    <a href="{{ path('app_album') }}" class="btn btn-secondary mt-3">⬅ Terug naar overzicht</a>
{% endblock %}
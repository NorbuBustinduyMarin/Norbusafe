<a href="{{ path('app_show_album', {'id': album.id}) }}">Toon</a>
<a href="{{ path('app_album_edit', {'id': album.id}) }}">Wijzig</a>

<form method="post" action="{{ path('app_album_delete', {'id': album.id}) }}" onsubmit="return confirm('Weet je zeker?');" style="display:inline;">
    <input type="hidden" name="_token" value="{{ csrf_token('delete' ~ album.id) }}">
    <button>Verwijder</button>
</form>

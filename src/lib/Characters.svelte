<script>
    export let character;
</script>

<div class="character">
    <img src={character.image} alt={character.name} />
    <ul>
        <li>{character.name}</li>
        <li>{character.species}</li>
    </ul>
     

  </div>
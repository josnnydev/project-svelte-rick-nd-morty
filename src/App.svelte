<script>

  import  Character from "./lib/Characters.svelte"
  let characters = [];
  let page = 1

  const getCharacters = async () => {
    const res = await fetch("https://rickandmortyapi.com/api/character?page="+page);

    const data = await res.json();

    characters = data.results;
  };

  getCharacters();

  function nextPage(){
    page++
    getCharacters()
  }

  function previousPage(){
    page--
    getCharacters()
  }
</script>

<h1 class="title">Rick and Morty Svelte</h1>



<div class="container">

  <div class="btns">
    <button class="btn" on:click={previousPage} disabled={page === 1}>...Previous</button>
    <button class="btn" on:click={nextPage}>Next...</button>
  </div>
  <div class="grid">
    {#each characters as character}
  <Character  {character}/>
    
  {/each}
  </div>
  
</div>

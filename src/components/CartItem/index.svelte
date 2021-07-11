<script>
  import Icon from '../Icon/index.svelte'

  export let Item = {
    name:"",
    price: 1,
    alreadyBought: false
  };

  export let Index;
  export let DeleteItem;
  export let setItemBought;

  console.log(Item)
</script>

<li>
  <div>
    {#if Item.alreadyBought == true}
      <span><s>{Item.name} - </s></span>
      <span><s>R$ {Item.price.toFixed(2)}</s></span>
    {:else}
      <span>{Item.name} - </span>
      <span> R$ {Item.price.toFixed(2)}</span>
    {/if}
  </div>
  <div class="buttonContainer">
    <button on:click={() => setItemBought(Index)}>
      <Icon name="Correct" fill="green" />
    </button>
    <button on:click={() => DeleteItem(Index)}>
      <Icon name="Remove" fill="red"/>
    </button>
  </div>
</li>


<style>
  li{
    margin-top: 12px;
    display: flex;
    box-shadow: 0px 0px 2.4px 0px gray;
    width: 300px;
    justify-content: space-between;
    align-items: center;
    height: 40px;
    padding: 2px 10px 2px 10px;
    border-radius: 4px;
  }

  .buttonContainer{
    height: 40px;
    display: flex;
    margin-top: 8px;
  }

  button{
    margin-left: 4px;
    margin-right: 4px;
    background-color: transparent;
    border: none;
    padding: 4px;
    border-radius: 4px;
    width: 30px;
    height: 30px;
    box-shadow: 0px 0px 2.4px 0px gray;
    cursor: pointer;
  }
</style>
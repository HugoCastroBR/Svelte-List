<script>

  import {getContext} from 'svelte';
  import CartItem from '../CartItem/index.svelte'

	let cart = getContext('cart');

  const DeleteItem = (index) => {
    const NewCart = [...$cart]
    NewCart.splice(index,1)
    $cart = NewCart
  }

  const setItemBought = (index) => {
    const NewCart = [...$cart]
    NewCart[index].alreadyBought === true ? NewCart[index].alreadyBought = false : NewCart[index].alreadyBought = true
    $cart = NewCart
  }
</script>


<ul>
  {#each $cart as Item,Index}
    <CartItem {Item} {Index} {DeleteItem} {setItemBought}/>
  {/each}
</ul>

<style>
  ul{
    display: flex;
    flex-direction: column;
    align-items: center;

    list-style-type:none;
  }
</style>
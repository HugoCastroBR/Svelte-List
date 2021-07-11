<script>
import App from "../../App.svelte";


  import Icon from '../Icon/index.svelte'


  import {getContext} from 'svelte';

	let cart = getContext('cart');

  const InputInfo = {name:"", price:0}

  const addToCart = () => {
    const NewCart = [...$cart]
    NewCart.push({...InputInfo})
    $cart = NewCart
  }

  
</script>

<div>
  <input placeholder="Add an item" on:change={(e) => InputInfo.name = e.target.value}/>
  <input placeholder="Price" type="number" class="priceInput" on:change={(e) => InputInfo.price = Number(e.target.value)}/>
  <button on:click={addToCart}>
    <Icon name="Plus" height="30px" width="30px"/>
  </button>
</div>

<style>
  div{
    display: flex;
    align-items: center;
    width: 100%;
    margin-left: 20px;
    justify-content: center;
  }
  input{
    margin-right: 8px;
    height: 40px;
  }
  .priceInput{
    width: 80px;
  }
  button{
    background-color: transparent;
    cursor: pointer;
    width: 40px;
    height: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
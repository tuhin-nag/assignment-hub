<script>

    import { createEventDispatcher } from 'svelte';
    let dispatch = createEventDispatcher();
    
    export let items;
    export let activeItem;
  
  </script>
  
  <div class="tabs">
    <ul>
      {#each items as item}
        <li on:click={() => dispatch('tabChange', item)}>
          <div class:active={item === activeItem}>{ item }</div>
        </li>
      {/each}
    </ul>
  </div>
  
  <style>
    .tabs{
      margin-bottom: 40px;
    }
    ul{
      text-align: left;
      display: flex;
      justify-content: left;
      padding: 0;
      list-style-type: none;
    }
    li{
      margin: 16px;
      font-size: 18px;
      color: #ffffff;
      cursor: pointer;
      
      padding: 8px;
      
    }
    li:hover{
      background-color: #6568a6;
      border-radius: 5px;
    }
    .active{
      color: #00e0c2;
      border-bottom: 2px solid #00e0c2;
      padding-bottom: 8px;
    }
  </style>
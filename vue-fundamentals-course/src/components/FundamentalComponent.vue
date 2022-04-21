<template>
<div class="header">
  	<h1>{{ header }}</h1>
    <button v-if="editing" class="btn btn-cancel" @click="doEdit(false)">
      Cancel
    </button>
    <button v-else class="btn btn-primary" @click="doEdit(true)">
      Add Item
    </button>
  </div>
  
    <form 
       class="add-item-form"
       @submit.prevent="saveItem"
       v-if="editing">
  
    <input 
           	type="text" 
           	v-model.trim="newItem" 
           	placeholder="Add an item" :maxlength="totalmaxinput" >
    
    <label>
      <input type="checkbox" v-model="newItemHighPriority"> High Priority
    </label>
    <button class="btn btn-primary" :disabled="newItem.length < 5">
      Save Item
    </button>
    
  </form>
	<p class="counter" v-if="editing">
      {{characterCount}}/{{totalmaxinput}}
    </p>  
  <ul>
    <li 
        v-for="(item,index) in reverseItem" 
        :key="item.id"
        :class="{strikeout:item.purchased,priority: item.highPriority}"
        @click="togglePurchased(item)"
    >
      	
      	{{id}}- {{item.label.toLocaleUpperCase()}}
    </li>
  </ul>
  <p v-if="!items.length">
    	Nothing to see here
  </p>
</template>
<script>
export default 
{
    name : 'FundamentalComponent',
    data(){
        return {
            header              :   'Shopping List',
            editing             :   false,
            newItem             :   '',
            newItemHighPriority :   false,
            totalmaxinput       :   20,
            items               :   [
                                        {id:1,label:"Fifa 2022",purchased:true,highPriority:false},
  									    {id:2,label:"NBA 2022",purchased:true,highPriority:false},
  									    {id:3,label:"Pacman",purchased:true,highPriority:true},
  									    {id:4,label:"NHl 2022",purchased:false,highPriority:true}
                                    ]
        }
    },
    computed:
    {
        characterCount()
        {
            return this.newItem.length;
        },
        reverseItem()
        {
            return [...this.items].reverse()
        }
    },
    methods : {
        doEdit(e)
        {
            this.editing = e;
            this.newItem="";
            this.newItemHighPriority ="";
        },
        togglePurchased(item)
        {
            item.purchased = !item.purchased;
        },
        saveItem()
        {
            this.items.push(
            {
                id:this.items.length+1,
                label:this.newItem,
                highPriority:this.newItemHighPriority
            });

            this.newItem="";    
            this.newItemHighPriority = "";        
        }
    }
}
</script>
<style>
  @import '../assets/base.css';
</style>
<template>
  <h1>Annuaire</h1>
  <h2>Retrouvez votre correspondant !</h2>

  <SearchBar v-bind="users" />
<hr>

<div class="containercard">
  <Card v-for="user in users" 
  :key="user.id" 
  :gender="user.gender" 
  :namefirst="user.name.first" 
  :namelast="user.name.last" 
  :email="user.email" 
  :phone="user.phone" 
  :img="user.picture.large"/>
</div>
</template>

<script >
import CardList from './CardList.vue';
import axios from 'axios';
import SearchBar from './SearchBar.vue';

export default {
 name: "Index",
 components: {
    Card: CardList,
    SearchBar
},

data(){
  return {
    users: [],
  }
},

mounted(){
 axios.get('https://randomuser.me/api/?results=12').then(response => {
  this.users = response.data.results
 }).catch(function (error) {
    //console.log(error);
  })
}

}
</script>

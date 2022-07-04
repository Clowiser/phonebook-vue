<script>
export default{
    name: "SearchBar",

    data() {
        return {
            searchUsers: [],
            search: '',
        }
    },

    methods: {
        search(){
           return this.searchUsers.filter((user => { 
             return user.gender.toLowerCase().includes(this.search.toLowerCase())
            }))
        },


        display(users){
            console.log(users);
        }
    }

}
</script>

<template>
    <input type="text" class="searchbar" placeholder="Rechercher par nom" v-model="search">
    <button type="submit" @click="search">Rechercher</button>
    <p>{{ search }}</p>
</template>

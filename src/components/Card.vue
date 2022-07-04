<script>
export default { 
    props: ['users','namefirst', 'namelast','email', 'phone', 'img' ],
}

</script>

<template>

  <div class="card">
    <img :src="img" alt="Avatar" class="img"/>
    <div class="description">
      <h4><b>{{namefirst}} {{namelast}} </b></h4>
      <p>{{email}}</p>
      <p>{{phone}}</p>
    </div>
  </div>


</template>
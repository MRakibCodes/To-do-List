<template>
  <div > 
    <md-card >
      <md-card-header>
        <div class="md-title">To-Do List</div>
      </md-card-header>
      <searchbar />
    </md-card>
  </div>

</template>

<script>
import searchbar from './searchbar.vue'

export default {
  name: 'mainBody',
  components: {
    searchbar
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.md-card {
        background: #42A5F5;
        color: #E3F2FD;
        display: inline-block;
        width: 500px;
        border-radius: 35px;
        padding: 20px;
        height: 500px;
      }


</style>

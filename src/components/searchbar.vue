<template>
  <div>    
    <div class="md-layout" style="padding-bottom: 10px">
      <div class="md-layout-item md-size-90">
        <md-field style="border-bottom: 2px dotted white">
          <label>Add Task</label>
          <md-textarea md-autogrow v-model="value" @keyup.enter="addListing"></md-textarea>
        </md-field>
      </div>
      <div class="md-layout-item md-size-10" style="padding-top: 20px;"> 
        <md-button class="md-icon-button md-raised add" v-on:click="addListing">
          <md-icon >add</md-icon>
        </md-button>
      </div>
    </div>
    
    <div style="overflow: auto; height: 290px">
      <div v-for="(listing, index) in todos" :key="index" class="md-layout" style="padding-top:10px; background: grey;padding-left: 7px; padding-right: 7px;
    border-bottom: 1px #ccc dotted; border-radius: 7px;">
        <input type="checkbox" class="md-layout-item md-size-5" v-on:change="markComplete(index)">
        <div class="md-layout-item md-size-80" v-bind:class="{'isComplete':listing.completed}" @click="markComplete(index)">
          <p>{{ listing.title }}</p>
        </div>
        <div class="md-layout-item md-size-5">
          <md-button class="md-icon-button md-raised add" v-on:click="remove(index)">
            <md-icon >clear</md-icon>
          </md-button>
        </div>
      </div> 
    </div>
    

  </div>
</template>

<script>
export default {
    name: 'searchbar',
    data() {
      return {
        value: "",
        todos: [{title: 'Learn JavaScript', completed: false}, {title: 'Learn Vue.js', completed: false}, {title: 'Build Something Awesome', completed: false}]

      }
    },
      methods: {
        addListing() {
          if (this.value) {
            this.todos.push({title: this.value, completed: false});
            this.value = null
            };
        },
        remove(no) {
          //var no = this.todos.indexOf(this.value)
          this.todos.splice(no,1)
        },
        markComplete(val) {
          this.todos[val].completed = !this.todos[val].completed;
        }
      }

} 

</script>

<style scoped>
  .add {
    color: aliceblue;
    
  }
  .isComplete {
    text-decoration: line-through;
    text-decoration-color: black;

  }
  p {
    text-align: left;
    
  }
  
</style>

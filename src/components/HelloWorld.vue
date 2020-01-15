<template>
  <div class="col-md-12">
    
      <div class="row mt-3" v-for="audience in audiences" :key="audience.id">
        <div class="col-sm-3">{{audience.id}}</div>
        <div class="col-sm-3">{{audience.name}}</div>
        <div class="col-sm-3">{{audience.location}}</div>
        <div class="col-sm-3">
          <button @click = "editAudience(audience)" class="btn btn-primary ml-2">Edit</button>
          
        </div>
        
      </div>

      <div class="mt-3">
        <form class="form-group col-sm-8 offset-sm-2">
          <input v-model = "audience.id" type="text" class="form-control" placeholder="">
          <input v-model = "audience.name" type="text" class="form-control mt-2" >
          <input v-model = "audience.location" type="text" class="form-control mt-2" >
        </form>
      </div>

      <div class="mt-4">
        <button @click = "addAudience" class="btn btn-primary ">Add Audience</button>      
      </div>
      
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  
  data(){
    return{
      audiences : [
        {
          "id": 1,
          "name" : "karim",
          "location" : "dhanmondi"
        },

        {
          "id": 2,
          "name" : "rahim",
          "location" : "dhanmondi"
        },

        {
          "id": 3,
          "name" : "solim",
          "location" : "dhanmondi"
        },

        {
          "id": 4,
          "name" : "rafik",
          "location" : "dhanmondi"
        }
      ],

      // person: {} gives reference problem. so it needs destructurig to solve
      // or we can use array
      audience : []
    }
  },

  methods: {
    addAudience(){
      this.audiences.push(this.audience)
      this.audience = []
    },

    editAudience(audience){
      this.audience = audience
    }
  }

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

<template>
    <div class="container">
    <form action="/action_page.php">
      <div class="mb-3 mt-3">
        <label for="em" class="form-label">FirstName:</label>
        <input
          type="text"
          class="form-control"
          id="email"
         
        v-model="firstName"/>
      </div>
      <p class="text-danger">{{message}}</p>
      <div class="mb-3 mt-3">
        <label for="em" class="form-label">Age</label>
        <input
          type="number"
          class="form-control"
        v-model="age"/>
        <p class="text-danger">{{messageAge}}</p>
      </div>
      <button type="submit" class="btn btn-primary" @click.prevent="res()">Submit</button>
      <button class="btn btn-success" style="margin:5px" @click.prevent="sum()">Count Number</button>
    </form>
    <h3 class="text-success">Information: {{Information}}</h3>

    <h2 class="text-primary">Count Number: {{count}}</h2>
  </div>
</template>

<script>


export default {
  name: "FormVue",
  components: {},
  data() {
    return {
      firstName: "",
      age: null,
      message:"",
      messageAge:"",
      count:0
    };
  },
  watch:{
    firstName(name){
      if(name.length<=3){
        this.message="Name must bigger than 3 letter"
      }else{
        this.message="";
      }
    },
    age(age){
      if(age<0){
        this.messageAge="Age must bigger than 0"
      }else{
        this.messageAge=""
      }
    }
  },
  computed:{
    Information(){
      return "name: "+this.firstName+' Age:'+this.age;
    }
  },
  methods:{
    res(){
      console.log(this.firstName);
    },
    sum(){
      this.count+=1;
    }
  }
};
</script>

<style scoped>
    form{
        border: 2px solid green;
        border-radius: 3px;
        height: 250px;
    }
</style>
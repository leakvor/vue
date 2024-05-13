<template>
  <div class="container">
    <h3 class="text-danger" v-if="fruits.length == 0">No data here</h3>
    <h3 class="text-success" v-else>Display list all data</h3>
    <table class="table">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Img</th>
          <th scope="col">Name</th>
          <th scope="col">Price</th>
          <th scope="col">Description</th>
          <th scope="col">Quantity</th>
          <th scope="col">Action</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="fruit in fruits" :key="fruit">
          <th scope="row">{{ fruit.id }}</th>
          <td><img :src="fruit.imageUrl" alt="" /></td>
          <td>{{ fruit.name }}</td>
          <td>{{fruit.price}}</td>
          <td>{{ fruit.description }}</td>
          <td>{{ fruit.quality }}</td>
          <td>
            <button class="btn btn-danger" @click="deleteFruit(index)">Delete</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  name: "TableVue",
  data() {
    return {
      fruits: [
        {
          id: 1,
          name: "Apple",
          price: "$1.00",
          description: "Fresh and crunchy apple",
          imageUrl:
            "https://cdn.britannica.com/22/187222-050-07B17FB6/apples-on-a-tree-branch.jpg",
          quality: 5,
        },
        {
          id: 2,
          name: "Banana",
          price: "$0.50",
          description: "Sweet and ripe banana",
          imageUrl:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT0nJ-ybSi5I_8ymqlVYga97exwBXQS3BRhTWWYcG6-cA&s",
          quality: 10,
        },
        // Add more fruits as needed
      ],
    };
  },
  methods:{
    deleteFruit(index){
      this.fruits.splice(index,1);
    },
  }
};
</script>

<style scoped>
img {
  width: 100px;
}
</style>

<template>
    <div class="container">

      <div class="row">
        <h2 class="display-2">Friends</h2>
    </div>

      <div class="row">
        <div class="spinner-border mx-auto" role="status" v-if="!friends.length">
        <span class="visually-hidden">Loading...</span>
        </div>
      </div>
      

      <div class="row gap-2">
        <Card v-for="friend in friends" :key="friend.id" :class="{'male': friend.gender == 'Male', 'female': friend.gender == 'Female'}">
          <template #cardHeader>
            <img
              :src="friend.profile"
              :alt="friend.firstName"
              loading="eager"
              class="img-fluid"/>
            
          
          </template>
          <template #cardBody>
            <p>{{ friend.firstName }} {{ friend.lastName }}</p>
          </template>
        </Card>
      </div>
    </div>
</template>

<script>
  import Card from "./Card.vue";
  
  export default {
    name: "FriendsComp",
    components: {
      Card
    },
  
    data() {
      return {
        friends: [
          {
            id: 1,
            firstName: "Jamin",
            lastName: "Langeveldt",
            gender: "Male",
            profile: "https://leahbasson.github.io/MyImages/images/Jamin.png",
          },
          {
            id: 2,
            firstName: "Katelin",
            lastName: "Bock",
            gender: "Female",
            profile: "https://leahbasson.github.io/MyImages/images/Katelin.png",
          },
          {
            id: 3,
            firstName: "Joel",
            lastName: "Mukanya",
            gender: "Male",
            profile: "https://leahbasson.github.io/MyImages/images/joel5.png",
          },
          {
            id: 4,
            firstName: "Tarryn",
            lastName: "Arendse",
            gender: "Female",
            profile: "https://leahbasson.github.io/MyImages/images/Tarryn.png",
          },
          {
            id: 5,
            firstName: "Zoë",
            lastName: "Saaiers",
            gender: "Female",
            profile: "https://leahbasson.github.io/MyImages/images/Zoe.png",
          },
        ],
      };
    },

    
  };
</script>
  
<style>
.male{
  border: 2px solid gold;
}

.female{
  border: 2px solid pink;
}
</style>
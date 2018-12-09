<template>
  <div>
    <h1>Hello {{ user.name }}!</h1>
    <h2>Your age is {{ user.age }}</h2>
  </div>
  
</template>

<script>
export default {
  data: () => {
    return { name: 'bal' };
  },

  async asyncData({app}){
    const user = await app.$axios.$get('api/me');

    console.log(user)
    return {user};
  },
};
</script>

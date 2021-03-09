<template>
  <div>
    <img src="../assets/Jokeimage.jpg" class="image" alt="joke image"/>
  </div>
</template>

<script>
export default {
  head() {
        return {
            title:'Welcome to giggly jokes',
            meta: [
                {
                    hid: 'decription',
                    name: 'description',
                    content: 'Best places for the jokes'
                }
            ]
        }
    },
}
</script>

<style>
.image {
  width:70%;
  height:70%;
  align-content: center;
}
</style>

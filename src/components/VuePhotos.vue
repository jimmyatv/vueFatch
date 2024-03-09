<template>
  <div v-for="(photo, idx) in photos" :key="idx" class="photos">
    <p>{{ photo.id }}</p>
    <p>{{ photo.title }}</p>
    <img :src="photo.url" alt="" />
  </div>
</template> 


<script>
export default {
    data() {
        return {
            photos: []
        }
    },
    async mounted() {
        try {
            const res = await fetch('https://jsonplaceholder.typicode.com/photos');
            const data = await res.json();

            this.photos = data;
            console.log(data)
            } catch (error) {
                console.error('Error fatching', error);
            }
    }
    
}
</script>


<style>
.photos {
  display: inline-block;
  margin-right: 20px;
  width: calc(50% - 40px);
  border: 1px solid blue;
}

.photos img {
    width: 100%;
    height: 100%;
    
}
</style>
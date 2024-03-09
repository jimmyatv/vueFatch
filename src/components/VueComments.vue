<template >
    <div 
    v-for="(comment, idx) in comments"
    class="User"
    :key="idx">
        <p>{{comment.name}}</p>
        <p>{{comment.comment}}</p>
        <p>{{comment.post}}</p>
    </div>
</template>


<script>
export default {
    data() {
        return {
            comments: [] 
        }
    },
    async mounted() { 
        try {
            const res = await fetch('comments.json');
            const data = await res.json(); 
            this.comments = data; 
        } catch (error) {
            console.error('Error fetching comments:', error);
        }
    }
}
</script>


<style scoped>
    
</style>
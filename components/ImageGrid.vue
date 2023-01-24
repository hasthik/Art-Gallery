<template>
    <div>
        <a href="#" @click.prevent="$router.back(-1)" id="blackText">images</a>
        <div>
        <div id="image-grid">
            <div class="image-container" v-for="(post, i) in posts" :key="i">
                <a :href="'https://picsum.photos/id/' + post.id + '/1000/1000'" download="proposed_file_name">
                <img :src="'https://picsum.photos/id/' + post.id + '/1000/1000'"  alt="image1" class="border w-100">
                </a>
                <p class="image-text"> {{ post.author }}</p>

            </div>
        </div>
    </div>
    </div>
    

</template>

<script>

export default {
    data() {
        return {
            posts: []
        }
    },
    activated() {
        // Call fetch again if last fetch more than 30 sec ago
        if (this.$fetchState.timestamp <= Date.now() - 30000) {
            this.$fetch()
        }
    },
    async fetch() {
        this.posts = await fetch('https://picsum.photos/v2/list?page=2&limit=100').then(res =>
            res.json()
        )
    }
}
</script>
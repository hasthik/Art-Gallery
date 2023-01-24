<template>

<div>
    <div id="imageContainer">
        <img src="https://picsum.photos/1920/1920"
            id="image" alt="">
        <div id="textContainer">Art Gallery</div>
        <a href="#" @click.prevent="$router.push('/images')" id="allImages">images</a>
    </div>
</div>
</template>

<script>
export default {
  name: 'Main',
  data() {
    return {
        // ...
    }
  },
}
</script>
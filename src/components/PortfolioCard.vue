<template>
    <article class="blog_item">
        <div class="blog_item_img">
            <img class="card-img rounded-0" :src="data.imgSrc" alt="">
        </div>
        <div class="blog_details">
            <a class="d-inline-block" :href="data.link" target="_blank">
                <h2>{{data.title}}</h2>
            </a>
            <p>{{ data.description }}</p>
        </div>
    </article>
</template>
<script>
export default {
    name: 'PortfolioCard',
    props: ['data']
}
</script>
<style></style>
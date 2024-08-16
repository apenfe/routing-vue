<template>

    <h1>Post View del elemento: {{postId}}</h1>

    <hr>

    <article v-if="post != null">

        <h2>{{post.title}}</h2>

        <p>{{post.body}}</p>

    </article>

    <article v-else>
        Cargando...
    </article>

    <hr>

    <RouterLink :to="{name: 'blog'}">Volver</RouterLink>

</template>

<script setup>

    import PostService from '@/services/PostService';
    import { onMounted, ref } from 'vue';
    import { useRoute } from 'vue-router';

    let postId = ref('');
    let post = ref(null);
    const service = new PostService();

    onMounted(async () => {

        const route = useRoute();
        postId.value = route.params.id;

        await service.fetchAll();
        const posts = service.getPosts().value;

        post.value = posts.find(p => p.id == postId.value);

    });

</script>
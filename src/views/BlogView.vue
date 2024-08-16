<template>

    <h1>Blog section</h1>

    <ul>
        <li><RouterLink :to="{name: 'post', params: {id: 1}}">Primer Post</RouterLink></li>
        <li><RouterLink :to="{name: 'post', params: {id: 2}}">Segundo Post</RouterLink></li>
        <li><RouterLink :to="{name: 'post', params: {id: 3}}">Tercer Post</RouterLink></li>
        <li><RouterLink :to="{name: 'post', params: {id: 4}}">Cuarto Post</RouterLink></li>
    </ul>

</template>
<script setup>
import {Head, Link, router} from "@inertiajs/vue3";
    defineProps({
        posts: Array,
    });

    const remove = async post => {
        if(confirm(`Remove post?`)){
            router.delete(`/post/${post.id}`);
        }
    }
</script>

<template>
    <Head title="Posts" />
    <div>
        <Link href="/post/create" class="btn btn-success">Create</Link>
    </div>
    <template v-if="posts.length > 0">
        <div v-for="post in posts">
            <div>Title: {{post.title}}</div>
            <div>Content: {{post.content}}</div>
            <div class="btn-group">
                <Link class="btn btn-primary" :href="`/post/${post.id}/edit`">Edit</Link>
                <button type="button" class="btn btn-danger" @click="remove(post)">Remove</button>
            </div>
            <hr>
        </div>
    </template>
    <div v-else>Post is empty!</div>
</template>

<style scoped>

</style>
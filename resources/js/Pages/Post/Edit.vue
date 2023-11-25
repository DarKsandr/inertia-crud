<script setup>
import {Head, Link, useForm} from "@inertiajs/vue3";

    const {post} = defineProps({
        method: {
            required: true,
            type: String
        },
        url: {
            required: true,
            type: String
        },
        title: {
            required: true,
            type: String
        },
        btnName: {
            required: true,
            type: String
        },
        post: {
            default: {},
            type: Object
        }
    })

    const form = useForm({
        title: post?.title,
        content: post?.content,
    });
</script>

<template>
    <Head>
        <title>{{title}}</title>
    </Head>
    <div>
        <h3 class="text-center">{{title}}</h3>
        <form @submit.prevent="form.submit(method, url)">
        <div class="mb-3">
            <label class="form-label">Title</label>
            <input type="text" class="form-control" v-model="form.title">
        </div>
            <div class="text-danger" v-if="form.errors.title">{{form.errors.title}}</div>
        <div class="mb-3">
            <label class="form-label">Content</label>
            <textarea class="form-control" rows="3" v-model="form.content"></textarea>
        </div>
            <div class="text-danger" v-if="form.errors.content">{{form.errors.content}}</div>
        <div>
            <button type="submit" :disabled="form.processing" class="btn btn-primary">{{btnName}}</button>
        </div>
        </form>
    </div>
</template>

<style scoped>

</style>
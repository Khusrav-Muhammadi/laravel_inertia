<template>
    <div class="w-96 mx-auto pt-8">
        <h1 class="text-lg mb-8">Posts</h1>
        <div class="mb-8">
            <Link :href="route('post.create')"
                  class="hover:bg-white hover:text-sky-500 border border-sky-500 block p-2 w-32 bg-sky-500 rounded-full text-center text-white">
                Add Post
            </Link>
        </div>
        <div v-if="posts">
            <div v-for="post in posts" class="mt-8 pt-8 border-t border-gray-300">
                <div>
                    id: {{ post.id }}
                </div>
                <div>
                    title: {{ post.title }}
                </div>
                <div>
                    content: {{ post.content }}
                </div>
                <div class="text-sm text-right">
                    {{ post.date }}
                </div>
                <div class="text-sm text-right">
                    <Link :href="route('post.show', post.id)" class="text-sky-500">show</Link>
                </div>
                <div class="text-sm text-right">
                    <Link :href="route('post.edit', post.id)" class="text-sky-500">edit</Link>
                </div>
                <div class="text-sm text-right">
                    <p @click="postDelete(post.id)" class="cursor-pointer text-red-500">delete</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import {Link} from "@inertiajs/vue3";

export default {
    name: "Index",
    components: {
        Link
    },
    props: [
        'posts'
    ],
    methods: {
        postDelete(id) {
            this.$inertia.delete('posts/' + id)
        }
    }
}
</script>

<style scoped>

</style>

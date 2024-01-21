<template>
    <div class="w-96 mx-auto pt-8">
        <h1 class="text-lg mb-8">Post</h1>
        <div class="mb-8">
            <Link :href="route('post.index')"
                  class="hover:bg-white hover:text-sky-500 border border-sky-500 block p-2 w-32 bg-sky-500 rounded-full text-center text-white">
                Back
            </Link>
        </div>
        <div class="mt-8 pt-8 border-t border-gray-300">
            <div>
                id: {{ post.id }}
            </div>
            <div>
                title: {{ post.title }}
            </div>
            <div>
                content: {{ post.content }}
            </div>
        </div>
    </div>

</template>

<script>
import {Link} from "@inertiajs/vue3";

export default {
    name: "Show",
    components: {
        Link
    },
    props: [
        'post'
    ],
}
</script>

<style scoped>

</style>

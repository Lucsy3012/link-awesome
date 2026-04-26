<template>
    <div class="max-w-md w-full">
        <div v-for="group in links" :key="group" class="flex flex-col mx-auto py-5">
            <h3 class="uppercase tracking-widest text-white text-opacity-85 font-medium text-sm text-left mb-3">{{ group.group }}</h3>
            <div v-for="link in group.links">
                <GroupLink :link="link" :key="link.title"/>
            </div>
        </div>
        <div class="uppercase tracking-widest text-white text-opacity-50 font-medium text-xs text-left mt-8 mb-3">
            <span>
              Original sourced: <a href="https://github.com/skaiwlkr/link-awesome" class="text-opacity-100 !underline" target="_blank" rel="noreferrer nofollow">skaiwlkr</a>
            </span>
        </div>
    </div>
</template>

<script setup>
const { data: links } = await useFetch('/api/links')

defineProps ({
    type: Object,
    required: true
})
</script>

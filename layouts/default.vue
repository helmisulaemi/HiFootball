<template>
    <div id="content">
        <app-header />
        <div class="container mx-auto mt-20">
            <Nuxt />
        </div>
    </div>
</template>
<script>
import Headers from '@/components/Headers.vue'
export default {
    components: {
        'app-header': Headers
    }
}
</script>
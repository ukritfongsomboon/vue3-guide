<template>
    <v-app>
        <navigation v-model="drawer"></navigation>
        <toolbar v-model="drawer"></toolbar>
        <v-main style="height: 100%; width: 100%">
            <!-- TODO Content for application -->
            <!-- TODO Content for application -->
        </v-main>
    </v-app>
</template>

<script>
import toolbar from '@/components/layouts/appbar.vue'
import navigation from '@/components/layouts/navigation.vue'
export default {
    name: 'App',
    components: {
        toolbar,
        navigation,
    },

    data: () => ({
        drawer: false,
    }),
}
</script>

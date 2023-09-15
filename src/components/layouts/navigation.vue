<template>
    <v-navigation-drawer
        location="left"
        :rail="!drawer"
        expand-on-hover
    >
        <template v-slot:prepend>
            <v-list>
                <v-list-item
                    prepend-avatar="https://randomuser.me/api/portraits/women/85.jpg"
                    title="Dashboard"
                    subtitle="Version 1.0.0"
                    lines="one"
                ></v-list-item>
            </v-list>
        </template>

        <v-divider></v-divider>

        <v-list
            density="compact"
            nav
            color="primary"
        >
            <v-list-item
                prepend-icon="mdi-folder-outline"
                title="Files"
                value="files"
            >
            </v-list-item>

            <v-list-item
                prepend-icon="mdi-home-outline"
                title="Home"
                value="home"
            >
            </v-list-item>

            <!-- <v-list-item
                    v-for="i in 30"
                    prepend-icon="mdi-star"
                    :title="`Starred-${i}`"
                    value="starred"
                >
                </v-list-item> -->

            <v-list-item
                prepend-icon="mdi-account-outline"
                title="Profile"
                value="profile"
            >
            </v-list-item>

            <v-divider></v-divider>
            <v-list-group>
                <template v-slot:activator="{ props }">
                    <v-list-item
                        v-bind="props"
                        prepend-icon="mdi-cog-outline"
                        title="Setting"
                    ></v-list-item>
                </template>
                <v-list-item
                    v-for="([title, icon], i) in cruds"
                    :key="i"
                    :value="title"
                    :title="title"
                    :prepend-icon="icon"
                ></v-list-item>
            </v-list-group>
            <v-divider></v-divider>
        </v-list>

        <template v-slot:append>
            <v-list
                density="compact"
                nav
                color="primary"
            >
                <v-list-item
                    prepend-icon="mdi-location-exit"
                    title="Logout"
                    value="logout"
                >
                </v-list-item>
            </v-list>
        </template>
    </v-navigation-drawer>
</template>

<script>
export default {
    setup() {
        return {}
    },
    data() {
        return {
            cruds: [
                ['Create', 'mdi-plus-outline'],
                ['Read', 'mdi-file-outline'],
                ['Update', 'mdi-update'],
                ['Delete', 'mdi-delete'],
            ],
        }
    },
    props: {
        modelValue: {
            type: Boolean,
            default: false,
        },
    },
    computed: {
        drawer: {
            get() {
                return this.modelValue
            },
            set(value) {
                this.$emit('update:modelValue', value)
            },
        },
    },
}
</script>

<style lang="scss" scoped></style>

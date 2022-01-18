<template>
    <span>
        <v-navigation-drawer
            app
            v-model="drawer"
            class="purple lighten-2"
            dark
            disable-resize-watcher
        >
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index" :to="item.url">
                        <v-list-tile-content>
                            {{ item.title }}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="purple darken-4" dark>
            <v-toolbar-side-icon
                class="hidden-md-and-up"
                @click="drawer = !drawer"
            ></v-toolbar-side-icon>
            <v-spacer class="hidden-md-and-up"></v-spacer>
            <router-link to="/">
                <v-toolbar-title data-cy="titleBtn">{{
                    appTitle
                }}</v-toolbar-title>
            </router-link>
            <v-btn
                flat
                class="hidden-sm-and-down nav-stem"
                to="/stem"
                data-cy="menuBtn"
                >STEM predmeti</v-btn
            >
            <v-btn
                flat
                class="hidden-sm-and-down nav-social"
                to="/social"
                data-cy="menuBtn"
                >Društveni predmeti</v-btn
            >
            <v-btn
                flat
                class="hidden-sm-and-down nav-development"
                to="/development"
                data-cy="menuBtn"
                >Daljnji razvoj</v-btn
            >
        </v-toolbar>
    </span>
</template>

<script>
export default {
    name: 'AppNavigation',
    data() {
        return {
            appTitle: 'Virtualni laboratoriji',
            drawer: false,
            items: [
                { title: 'STEM predmeti', url: '/stem' },
                { title: 'Društveni predmeti', url: '/social' }
            ]
        };
    }
};
</script>

<style scoped>
a {
    color: white;
    text-decoration: none;
}
</style>

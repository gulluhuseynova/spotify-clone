<template>
    <v-navigation-drawer permanent app width="190px">
        <img src="../assets/logo.svg" alt="spotifyLogo" width="160px" height="50px" style="margin-top: 10px" />

        <v-list dense nav style="margin-left: 5px" flat v-model="selectedItem">
            <v-list-item v-for="item in items" :key="item.title" link>
                <v-list-item-icon style="margin-right: 15px">
                    <v-icon style="color: #b3b3b3">{{ item.icon }}</v-icon>
                </v-list-item-icon>
                <v-list-item-content class="list-class">
                    <v-list-item-title style="font-size: 14px">{{ item.title }}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
        <v-list dense nav style="margin-left: 5px" flat>
            <v-list-item v-for="song in favSongs" :key="song.title" link>
                <v-list-item-icon style="margin-right: 15px">
                    <v-icon style="color: #b3b3b3">{{ song.icon }}</v-icon>
                </v-list-item-icon>
                <v-list-item-content class="list-class">
                    <v-list-item-title style="font-size: 14px">{{ song.title }}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <div>
            <v-img class="expanded-album" src="@/assets/Grande.jpg"></v-img>
        </div>
    </v-navigation-drawer>
</template>

<script>
export default {
    name: "Navigation",
    data() {
        return {
            selectedItem: 1,
            options: ["File", "Edit", "View", "Playback", "Help"],
            items: [
                { title: "Home", icon: "mdi-home-variant" },
                { title: "Search", icon: "mdi-magnify" },
                { title: "Your Library", icon: "mdi-bookshelf" },
            ],
            favSongs: [
                { title: "Create Playlist", icon: "mdi-plus-box" },
                { title: "Liked Songs", icon: "mdi-cards-heart-outline" },
            ],
            right: null,
        };
    },
    methods: {},
};
</script>

<style lang="scss" scoped>
::v-deep .v-navigation-drawer__content {
    position: relative !important;

    .list-class {
        color: #b3b3b3;
        transition: all 0.3s ease-out;
        -webkit-transition: all 0.3s ease-out;

        &:hover {
            color: white;
        }
    }
    .expanded-album {
        position: absolute;
        bottom: 0;
    }
}
</style>

<template>
    <v-app-bar dense class="fixed-bar">
        <v-row>
            <v-col cols="auto">
                <v-btn fab x-small text>
                    <v-icon large>mdi-chevron-left</v-icon>
                </v-btn>
            </v-col>
            <v-col cols="auto">
                <v-btn fab x-small text>
                    <v-icon large>mdi-chevron-right</v-icon>
                </v-btn>
            </v-col>
        </v-row>

        <v-spacer />

        <div class="text-center">
            <v-menu offset-y >
                <template v-slot:activator="{ on, attrs }">
                    <v-btn color="dark" dark v-bind="attrs" v-on="on" rounded small max-width="140">
                        <img src="@/assets/ariana.jpeg" alt="profil" height="25" style="border-radius: 15px" class="ma-1" />
                        GulHuseynli
                        <v-icon>mdi-menu-down</v-icon>
                    </v-btn>
                </template>
                <v-list id="profile-menu">
                    <v-list-item v-for="(item, index) in items" :key="index" @click="() => {}">
                        <v-list-item-title class="title-font">{{ item.title }}</v-list-item-title>
                        <v-divider></v-divider>
                    </v-list-item>
                    <div id="dropdown-line"></div>
                    <v-list-item @click="() => {}">
                        <v-list-item-title class="title-font">{{ logout[0] }}</v-list-item-title>
                    </v-list-item>
                </v-list>
            </v-menu>
        </div>
    </v-app-bar>
</template>

<script>
export default {
    name: "AppBar",
    data: () => ({
        items: [{ title: "Account" }, { title: "Profile" }, { title: "Private Session" }, { title: "Settings" }],
        logout: ["Log out"],
    }),
};
</script>

<style lang="scss" scoped>
#dropdown-line {
    background-color: #282828;
    border: none;
    height: 1px;
    margin: 8px var(--left-sidebar-padding-right) 0 var(--left-sidebar-padding-left);
    min-height: 1px;
}
#profile-menu {
    margin-top: 15px;

    .title-font {
        font-size: 14px;
    }
}
.fixed-bar {
    position: sticky;
    top: 0;
    z-index: 1;
    background-color: black !important;
}
</style>

<template>
    <v-app>
        <v-container fluid style="padding: 0 25px">
            <Navigation id="navigation" />
            <v-main>
                <AppBar />
                <v-row>
                    <v-col>
                        <div class="greeting">{{ greeting[0] }}</div>
                    </v-col>
                </v-row>
                <v-row>
                    <v-col v-for="n in 6" :key="n">
                        <RecentAlbums />
                    </v-col>
                </v-row>
                <v-row v-for="rowInfo in rowLinks" :key="rowInfo.name">
                    <v-col>
                        <AlbumsCard :rowInfo="rowInfo" />
                    </v-col>
                </v-row>
                <!-- Footer -->
                <v-row>
                    <v-col>
                        <v-row>
                            <FooterLinks v-for="footerElem in footerElems" :key="footerElem.title" :link="footerElem" />
                            <v-spacer></v-spacer>
                            <v-col style="margin-top: 15px" cols="auto" v-for="btn in footerMenuMediaBtns" :key="btn.name">
                                <v-btn class="footer-btn" elevation="2" fab small>
                                    <v-icon class="footer-icon">{{ btn.name }}</v-icon>
                                </v-btn>
                            </v-col>
                        </v-row>
                        <v-row class="footer-bottom">
                            <v-col class="footer-link" cols="auto" v-for="link in footerBottomLinks" :key="link.name">
                                {{ link.name }}
                            </v-col>
                            <v-spacer></v-spacer>
                            <v-col cols="auto" style="color: #919496; font-size: 12px"> © 2022 Spotify AB </v-col>
                        </v-row>
                    </v-col>          
                </v-row>
            </v-main>   
            <Footer />
        </v-container>
    </v-app>
</template>

<script>
import Navigation from "./components/Navigation.vue";
import Footer from "./components/Footer.vue";
import AppBar from "./components/AppBar.vue";
import AlbumsCard from "./components/AlbumsCard.vue";
import RecentAlbums from "./components/RecentAlbums.vue";
import FooterLinks from "./components/FooterLinks.vue";

export default {
    name: "App",

    components: { Navigation, Footer, AppBar, AlbumsCard, RecentAlbums, FooterLinks },

    data: () => ({
        rowLinks: [
            {
                name: "Episodes for you",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Based on your recent listening",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Recently played",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Uniquely yours",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Made for GülHuseynlee",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Your Favorite Artists",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "100% Global",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
            {
                name: "Discover something new",
                link: "http://localhost:8080/2",
                cards: [
                    { image: require("@/assets/amelia.jpeg") },
                    { image: require("@/assets/piano.jpeg") },
                    { image: require("@/assets/ariana.jpeg") },
                    { image: require("@/assets/weeknd.jpeg") },
                    { image: require("@/assets/swedishHM.jpeg") },
                ],
                albumName: ["Hit Rewind","Chill Mix","Happy Mix","Daily Mix","Pop Rising","Fresh & Chill"],
            },
        ],
        footerElems: [
            {
                title: "Company",
                children: [
                    { name: "About", companyLinks: "http://localhost:8080/2" },
                    { name: "Jobs", companyLinks: "http://localhost:8080/2" },
                    { name: "For the Record", companyLinks: "http://localhost:8080/2" },
                ],
            },
            {
                title: "Communities",
                children: [
                    { name: "For Artists", companyLinks: "http://localhost:8080/2" },
                    { name: "Developers", companyLinks: "http://localhost:8080/2" },
                    { name: "Advertising", companyLinks: "http://localhost:8080/2" },
                    { name: "Investors", companyLinks: "http://localhost:8080/2" },
                    { name: "Vendors", companyLinks: "http://localhost:8080/2" },
                ],
            },
            {
                title: "Useful Links",
                children: [
                    { name: "Support", companyLinks: "http://localhost:8080/2" },
                    { name: "Web Player", companyLinks: "http://localhost:8080/2" },
                    { name: "Free Mobile App", companyLinks: "http://localhost:8080/2" },
                ],
            },
        ],
        footerMenuMediaBtns: [
            { name: "mdi-instagram", btnLink: "http://localhost:8080/2" },
            { name: "mdi-twitter", btnLink: "http://localhost:8080/2" },
            { name: "mdi-facebook", btnLink: "http://localhost:8080/2" },
        ],
        footerBottomLinks: [
            { name: "Legal", link: "http://localhost:8080/2" },
            { name: "Privacy Center", link: "http://localhost:8080/2" },
            { name: "Privacy Policy", link: "http://localhost:8080/2" },
            { name: "Cookie Settings", link: "http://localhost:8080/2" },
            { name: "About Ads", link: "http://localhost:8080/2" },
        ],
        scrollInvoked: 0,
        greeting: ["Good morning", "Good afternoon", "Good evening"],
    }),
    methods: {
        onScroll() {
            this.scrollInvoked++;
        },
    },
};
</script>

<style lang="scss" scoped>
.greeting {
    font-size: 30px;
    font-weight: bold;
    padding-top: 20px;
}

.footer-btn:hover .footer-icon {
    color: #1ed760;
}

.footer-bottom {
    margin: 90px 30px 20px;
    color: #919496;
    font-size: 10px;

    .footer-link {
        cursor: pointer;
        margin-right: 40px;

        &:hover {
            color: #1ed760;
        }
    }
}

@media only screen and (min-width: 601px) {
    #navigation {
        display: block;
    }
}

@media only screen and (max-width: 600px) {
    #navigation {
        display: none;
    }
}
</style>

<style lang="scss">
a {
    text-decoration: none;
    color: white !important;
}

// Animations
.show-anim {
    transition: opacity 0.3s ease-in;
    .show-child {
        // visibility: hidden;
        opacity: 0;
    }

    &:hover .show-child {
        // visibility: visible;
        opacity: 1;
    }
}

.scale-anim:hover {
    transition: transform 0.1s;
    transform: scale(1.1);
}
</style>

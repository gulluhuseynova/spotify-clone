<template>
    <v-col cols="auto">
        <v-row class="footer-title" dense>
            <v-col>{{ link.title }}</v-col>
        </v-row>
        <v-row class="footer-child" v-for="child in link.children" :key="child.name" dense>
            <v-col>{{ child.name }}</v-col>
        </v-row>
    </v-col>
</template>

<script>
export default {
    name: "FooterLinks",
    props: ["link"],
};
</script>

<style lang="scss" scoped>
.footer-title {
    color: #919496;
    font-size: 12px;
    font-weight: 900;
    letter-spacing: 0.08em;
    line-height: 1.4;
    text-transform: uppercase;
    margin: 30px;
}

.footer-child {
    cursor: pointer;
    color: white;
    padding: 3px 0px 2px;
    font-size: 16px;
    font-weight: 400;
    line-height: 0.5;
    margin: 30px 45px 20px 30px;

    &:hover {
        color: #1ed760;
    }
}

</style>

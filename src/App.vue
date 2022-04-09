<template>
    <div>
        test
        <ul>
            <li v-for="item in users" :key="item.id">{{ item.name }}</li>
        </ul>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: "App",
    data() {
        return {
            users: []
        };
    },
    mounted() {
        axios.get("http://localhost:8080/api/users").then((res) => {
            this.users = res.data;
        });
    },
};
</script>

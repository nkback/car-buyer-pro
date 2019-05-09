<template>
    <div id="app">
        <h1>{{header}}</h1>
    </div>
</template>
<script>
    import axios from 'axios';
    export default {
        data () {
            return {
                header: "Welcome to Car Buyer Pro",
                bkg: chrome.extension.getBackgroundPage(),
            }
        },
        mounted() {
            let vm = this;
            axios.get("https://my-json-server.typicode.com/typicode/demo/posts")
                .then((data) => {
                    vm.bkg.console.log(data);
                });
        }
     }
</script>
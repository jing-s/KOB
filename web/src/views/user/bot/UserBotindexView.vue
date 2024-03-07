<template>
    <ContentField>
        userbot
    </ContentField>
</template>

<script>
import ContentField from '../../../components/ContentField.vue'
import $ from 'jquery'
// import { useStore } from 'vuex'

export default {
    components: {
        ContentField
    },
    setup() {
        // const store = useStore();
        const jwt_token=localStorage.getItem("jwt_token");//取出token

        // $.ajax({
        //     url: "http://127.0.0.1:3000/user/bot/add/",
        //     type: "post",   //  大小写都行
        //     data: {
        //         title: "Bot的标题",
        //         description: "Bot的描述",
        //         content: "Bot的代码",
        //     },
        //     headers: {
        //         // Authorization: "Bearer " + store.state.user.token,   //  报跨域错误
        //         Authorization:"Bearer "+ jwt_token, 
        //     },
        //     success(resp) {
        //         console.log("addbot_success" + resp);
        //     },
        //     error(resp) {
        //         console.log("addbot_error" + resp);
        //     }

        // })

        // $.ajax({
        //     url: "http://127.0.0.1:3000/user/bot/remove/",
        //     type: "post",
        //     data: {
        //         bot_id: 3,
        //     },
        //     headers: {
        //         Authorization: "Bearer " + jwt_token,
        //     },
        //     success(resp) {
        //         console.log(resp);
        //     },
        //     error(resp) {
        //         console.log(resp);
        //     },
        // })

        // $.ajax({
        //     url: "http://127.0.0.1:3000/user/bot/update/",
        //     type: "post",   //  大小写都行
        //     data: {
        //         bot_id: 4,
        //         title: "Bot的标题4",
        //         description: "Bot的描述4",
        //         content: "Bot的代码4",
        //     },
        //     headers: {
        //         // Authorization: "Bearer " + store.state.user.token,   //  报跨域错误
        //         Authorization:"Bearer "+ jwt_token, 
        //     },
        //     success(resp) {
        //         console.log("addbot_success" + resp);
        //     },
        //     error(resp) {
        //         console.log("addbot_error" + resp);
        //     }

        // })

        $.ajax({
            url: "http://127.0.0.1:3000/user/bot/getlist/",
            type: "get",
            headers: {
                Authorization: "Bearer " + jwt_token,
            },
            success(resp) {
                console.log(resp);
            },
            error(resp) {
                console.log(resp);
            },
        })

    }
}
</script>

<style scoped>
</style>
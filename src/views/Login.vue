<template>
    <div id="login">
        <h1>Đăng nhập</h1>
        <input class="input-login" type="text" name="username" v-model="input.username" placeholder="Username" />
        <input class="input-login" type="password" name="password" v-model="input.password" placeholder="Password" />
        <button type="button" v-on:click="login()">Đăng nhập</button>
    </div>
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                    if(this.input.username == "quandaihiep" && this.input.password == "password") {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "home" });
                    } else {
                        alert("Tài khoản hoặc mật khẩu của bạn nhập không đúng");
                    }
                } else {
                    alert("Vui lòng nhập tài khoản và mật khẩu");
                }
            }
        }
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 1px solid #CCCCCC;
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 200px;
        padding: 20px;
    }
    
    #login h1 {
        text-align: center;
        color: green;
    }
    .input-login {
        width: 460px;
        margin: 20px 0;
        padding: 4px;
        border-radius: 5px;
    }

    #login button {
        border-radius: 5px;
        background-color: green;
        margin-left: 180px;
    }
</style>
<template>
    <div class="container">
        <h1 class="login_head">
            Please enter your
        </h1>
        <form class="login_form">
            <div class="login_element">
                <span class="login_input_name">
                    login
                </span>
                <input class="login_input" type="text" name="email">
            </div>
            <div class="login_element">
                <span class="login_input_name">
                    password
                </span>
                <input class="login_input" type="text"  name="password">
            </div>
            <button>
                Send
            </button>
        </form>
        <span class="access_list_head">
            super secret passwords list
        </span>
        <div class="access_list">
            <div class="access_element">
                <span class="access_element_text">
                    login: <strong>123123@mail.ru</strong>
                </span>
                <span class="access_element_text">
                    password: <strong>123456</strong>
                </span>
            </div>
            <div class="access_element">
                <span class="access_element_text">
                    login: <strong>999999@mail.ru</strong>
                </span>
                <span class="access_element_text">
                    password: <strong>123456</strong>
                </span>
            </div>
        </div>
    </div>
</template>

<script>

</script>

<style scoped>
.container{
    max-width: 1220px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 20px;
    padding-right: 20px;
}

.login_head{
    font-size: 36px;
    margin-top: 60px;
    margin-bottom: 60px;
}

.login_form{
    max-width: 780px;
    width: 100%;
    margin-right: auto;
    background: #fff;
    box-shadow: 0px 2px 16px rgba(0,0,0,0.06);
    border-radius: 12px;
    overflow: hidden;
    padding: 36px 24px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    margin-bottom: 160px;
}

.login_element{
    display: flex;
    flex-direction: column;
    max-width: 260px;
}

.login_input_name{
    margin-bottom: -6px;
    z-index: 2;
    background: #ffffff;
    display: block;
    width: fit-content;
    padding: 0 4px;
    margin-left: 10px;
}

.login_input{
    padding: 12px;
    font-size: 24px;
    border-radius: 7px;
}

.access_list_head{
    font-size: 32px;
    display: flex;
    justify-content: flex-end;
}

.access_list{
    display: flex;
    gap: 24px;
    margin-bottom: 120px;
    margin-top: 30px;
}

.access_element{
    box-shadow: 0px 2px 16px rgba(0,0,0,0.06);
    border-radius: 12px;
    overflow: hidden;
    padding: 36px 24px;
    width: 100%;
    display: flex;
    gap: 12px;
    flex-direction: column;
}

.access_element_text{
    font-size: 20px;
}

@media(max-width: 768px){
    .access_list{
        flex-direction: column;
    }

    .access_element{
        flex-direction: column;
    }
}
</style>

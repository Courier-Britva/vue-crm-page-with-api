<template>
    <div class="header">
        <div class="container">
            <header class="header_content">
                <button class="logout_button" @click="logoutUser">
                    Logout
                </button>
            </header>

            <main class="main">

            </main>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        getCookie(name) {
            const value = `; ${document.cookie}`;
            const parts = value.split(`; ${name}=`);
            if (parts.length === 2) return parts.pop().split(';').shift();
        },

        logoutUser() {
            fetch('/logout', {
                method: 'POST',
                headers: {
                'Content-Type': 'application/json',
                'Accept': 'application/json',
                'X-XSRF-TOKEN': decodeURIComponent(this.getCookie('XSRF-TOKEN')),
                },
                credentials: 'include',
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error('Logout failed');
                }
                location.replace('/login');
            })
            .catch(error => {
                console.error('Error:', error);
            });
        },
    }
};
</script>

<style scoped>
.container{
    max-width: 1220px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 20px;
    padding-right: 20px;
}

.header{
    position: fixed;
    top: 0;
    z-index: 2;
    background: #fff;
    box-shadow: 0px 2px 16px rgba(0,0,0,0.06);
    width: 100%;
    height: 70px;
}

.header>*{
    height: 100%;
}

.main{
    margin-top: 70px;
}

.header_content{
    display: flex;
    justify-content: flex-end;
    width: 100%;
    height: 100%;
    align-items: center;
}

.logout_button{
    font-size: 14px;
    background-color: #ffffff;
    border: 1px solid #000000;
    color: #000000;
    outline: none;
    transition: all .3s ease-out;
    padding: 8px 12px;
    cursor: pointer;
    border-radius: 7px;
}

.logout_button:hover{
    background-color: #000000;
    color: #ffffff;
}
</style>

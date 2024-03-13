<template>
    <div class="header">
        <div class="container">
            <header class="header_content">
                <button class="logout_button" @click="logoutUser">
                    Logout
                </button>
            </header>
        </div>
    </div>
    <main class="main">
        <div class="container">
            <div class="main_content">
                <table>
                    <thead>
                        <tr>
                            <th>#</th>
                            <th>Date Register</th>
                            <th>Client Name</th>
                            <th>Manager</th>
                            <th>Program Type</th>
                            <th>Program Price</th>
                        </tr>
                    </thead>
                    <tbody class="main_tbody">
                        <tr v-for="(item, index) in payPlanItem.data" :key="item.id">
                            <td>{{ index + 1 }}</td>
                            <td>{{ item.date_register }}</td>
                            <td>{{ item.client_name }}</td>
                            <td>{{ item.manager.name }}</td>
                            <td>{{ item.program_type }}</td>
                            <td>{{ item.program_price }}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </main>
</template>

<script>
import { Inertia } from '@inertiajs/inertia';

export default {
    props: {
        payPlanItem: {
            type: Object,
            default: () => ({
                current_page: 1,
                data: [],
                // include other keys as needed or leave them out for simplicity
            }),
        },
    },
    mounted() {
        console.log(this.payPlanItem); // Check the received prop
    },
    methods: {
        logoutUser() {
            Inertia.post('/logout');
        },
    }
};
</script>

<style scoped>
tr{
    height: 36px;
}
td{
    min-width: 200px;
}

th{
    text-align: left;
}

.main_tbody{
    border-spacing: 0 10px;
}

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

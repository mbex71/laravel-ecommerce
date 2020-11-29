<template>
    <app-layout>
        <h1>Login</h1>
        <form @submit.prevent="onSubmit">
            <div>

                <input type="text" v-model="form.email">
            </div>
            <div>

                <input type="text" v-model="form.password">
            </div>
            <button type="submit">Submit</button>
        </form>
    </app-layout>
</template>
<script>
import AppLayout from '@/Layouts/AppLayout'
export default {
    data(){
        return{
            form:{
                email:'',
                password:''
            }
        }
    },
    components:{
        AppLayout
    },
    methods:{
        onSubmit(){
            this.$inertia.post('/login', this.form)
        }
    }
    
}
</script>
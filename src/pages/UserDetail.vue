<template>
    <q-page class="flex column align-center q-ma-sm q-pa-md bg-deep-purple-1">
        <h5>회원 상세 정보</h5>
        <q-separator class="q-my-md" />

        <q-list separator>

            <q-item :key="index" v-for="(item, name, index) in value" clickable v-ripple class="q-py-lg">
                <q-item-section>{{ name }}: </q-item-section>
                <q-item-section>{{ item }}</q-item-section>
            </q-item>

            <!-- <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>hasDog: </q-item-section>
                <q-item-section>{{ hasDogKr }}</q-item-section>
            </q-item> -->

        </q-list>     

    </q-page>
</template>

<script>

export default {
    name: 'User Detail',
    // props: ['email', 'password', 'name', 'address', 'phone', 'hasDog'],
    props: {
        value: {
            email: '',
            password: '',
            name: '',
            address: '',
            phone: '',
            hasDog: null
        }
    },
    created() {
        console.log(this.value);
    },
    methods: {

    },

    computed: {
        hasDogKr() {
            return this.value.hasDog === true ? '있음' : '없음'
        }
    }
}
</script>

<template>
    <q-page class="flex column align-center q-ma-sm q-pa-md bg-deep-purple-1">
        <h5>회원 상세 정보</h5>
        <q-separator class="q-my-md" />

        <q-list separator>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>Email: </q-item-section>
                <q-item-section>{{ email }}</q-item-section>
            </q-item>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>Password: </q-item-section>
                <q-item-section>{{ password }}</q-item-section>
            </q-item>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>Name: </q-item-section>
                <q-item-section>{{ name }}</q-item-section>
            </q-item>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>Address: </q-item-section>
                <q-item-section>{{ address }}</q-item-section>
            </q-item>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>Phone: </q-item-section>
                <q-item-section>{{ phone }}</q-item-section>
            </q-item>

            <q-item clickable v-ripple class="q-py-lg">
                <q-item-section>hasDog: </q-item-section>
                <q-item-section>{{ hasDogKr }}</q-item-section>
            </q-item>

        </q-list>     

    </q-page>
</template>

<script>

export default {
    name: 'User Detail',
    props: ['email', 'password', 'name', 'address', 'phone', 'hasDog'],
    computed: {
        hasDogKr() {
            return this.hasDog === true ? '있음' : '없음'
        }
    }
}
</script>

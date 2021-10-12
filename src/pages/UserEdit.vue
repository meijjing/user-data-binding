<template>
    <q-page class="flex column align-center q-ma-sm q-pa-md bg-grey-2">
        <h5>회원 정보 수정</h5>
        <q-separator class="q-my-md" />

        <q-list separator>
            <q-item clickable v-ripple>
                <q-item-section>Email: </q-item-section>
                <q-input filled v-model="user.email" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>Password: </q-item-section>
                <q-input filled type="password" v-model="user.password" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>Password: </q-item-section>
                <q-input filled type="password" v-model="re_pwd" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>Name: </q-item-section>
                <q-input filled v-model="user.name" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>Address: </q-item-section>
                <q-input filled v-model="user.address" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>Phone: </q-item-section>
                <q-input filled v-model="user.phone" />
            </q-item>

            <q-item clickable v-ripple>
                <q-item-section>hasDog: </q-item-section>
                <!-- <q-input v-model="user.hasDog" /> -->


                <q-item-section>
                    <q-option-group 
                    :options="options"
                    type="radio"
                    v-model="user.hasDog"
                    />
                </q-item-section>
            </q-item>
        </q-list>    

        <q-btn @click="changeUser" color="deep-purple-12" label="Update" class="q-mt-md" />


    </q-page>
</template>

<script>
export default {
    name: 'User Edit',
    props: ['email', 'password', 'name', 'address', 'phone', 'hasDog'],
    data() {
        return {
            re_pwd: '',
            user: {
                email: '',
                password: '',
                name: '',
                address: '', 
                phone: '',
                hasDog: null
            }
        }
    },
    setup() {
        return {
            options: [
                {
                    label: '반려견 있음',
                    value: true
                },
                {
                    label: '반려견 없음',
                    value: false
                },
            ]
        }
    },
    created() {
        this.user.email = this.email
        this.user.password = this.password
        this.user.name = this.name
        this.user.address = this.address
        this.user.phone = this.phone
        this.user.hasDog = this.hasDog
    },
    methods: {
        changeUser() {
            if (this.user.password != this.re_pwd) {
                alert('비밀번호를 확인해주세요.')
                return false;
            }
            console.log(this.user);
            this.$emit("child", this.user)
        }
    }


}
</script>

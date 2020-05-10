<template>
  <div class="blue lighten-3 pa-8 ma-5">
    <h1>User 컴포넌트</h1>
    <p>정보창</p>
    <p>{{ getDateAndTime(createdAt) }}</p>
    <v-container>
        <v-layout row wrap>
        <v-flex xs12 sm6>
            <UserDetail
                :name="name"
                :address="address"
                :phone="phone"
                :hasDog="hasDog"
            />
        </v-flex>
        <v-flex xs12 sm6>
            <UserEdit
                :name="name"
                :address="address"
                :phone="phone"
                :hasDog="hasDog"
                @child="parents"
            />
        </v-flex>
        </v-layout>
    </v-container>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue'
import UserEdit from './UserEdit.vue'
import { dateFormat } from '../mixins/dateFormat'
export default {
  components: {
    UserDetail,
    UserEdit
  },
  data () {
    return {
      name: 'Ki Jun',
      address: 'Suwon',
      phone: '010-1111-1111',
      hasDog: true,
      createdAt: null
    }
  },
  created () {
    this.createdAt = new Date()
  },
  methods: {
    parents (user) {
      this.name = user.name
      this.address = user.address
      this.phone = user.phone
      this.hasDog = user.hasDog
    }
    // getDateAndTime (date) {
    //   const hour = date.getHours()
    //   const minutes = date.getMinutes()
    //   const fullDate = `${date.getFullYear()}/${date.getMonth() + 1}/${date.getDate()}`
    //   return `${fullDate} ${hour} : ${minutes}`
    // }
  },
  mixins: [dateFormat]
}
</script>

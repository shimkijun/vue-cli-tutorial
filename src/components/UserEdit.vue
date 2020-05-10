<template>
  <div class="yellow lighten-3 pa-3">
    <h3>회원 정보를 수정할 수 있습니다.</h3>
    <p>수정사항</p>
    <v-text-field
        label="name"
        v-model="user.name"
    />
    <v-text-field
        label="address"
        v-model="user.address"
    />
    <v-text-field
        label="phone"
        v-model="user.phone"
    />
    <v-radio-group v-model="user.hasDog">
        <v-radio
            label="반려견 있음"
            :value="true"
        />
        <v-radio
            label="반려견 없음"
            :value="false"
        />
        <v-btn @click="changeUser" color="primary">수정 완료</v-btn>
    </v-radio-group>
  </div>
</template>
<script>
import { eventBus } from '../main.js'

export default {
  props: ['name', 'address', 'phone', 'hasDog'],
  data () {
    return {
      user: {}
    }
  },
  created () {
    this.user.name = this.name
    this.user.address = this.address
    this.user.phone = this.phone
    this.user.hasDog = this.hasDog
  },
  methods: {
    changeUser () {
      this.$emit('child', this.user)
      // eventBus.$emit('userWasEdited', new Date())
      eventBus.userWasEdited(new Date())
    }
  }
}
</script>

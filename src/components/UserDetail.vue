<template>
  <div class="red lighten-3 pa-3">
    <h3>자세한 회원 정보를 확인합니다.</h3>
    <p>상세사항</p>
    <v-list dense>
      <v-list-item>
        <v-list-item-content>이름 : {{ name }}</v-list-item-content>
      </v-list-item>
      <v-list-item>
        <v-list-item-content>주소 : {{ address }}</v-list-item-content>
      </v-list-item>
      <v-list-item>
        <v-list-item-content>휴대전화 : {{ phone }}</v-list-item-content>
      </v-list-item>
      <v-list-item>
        <v-list-item-content>반려동물 : {{ hasDogKr }}</v-list-item-content>
      </v-list-item>
      <v-list-item>
        <v-list-item-content>수정일자 : {{ editedDate }}</v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>
<script>
import { eventBus } from '../main.js'

export default {
  props: ['name', 'address', 'phone', 'hasDog'],
  data () {
    return {
      editedDate: null
    }
  },
  computed: {
    hasDogKr () {
      return this.hasDog === true ? '있음' : '없음'
    }
  },
  created () {
    eventBus.$on('userWasEdited', (date) => {
      this.editedDate = date
    })
  }
}
</script>

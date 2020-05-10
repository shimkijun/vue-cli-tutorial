<template>
  <div class="blue lighten-3 pa-12 ma-10">
    <h1>User 컴포넌트</h1>
    <p>이름: </p>
    <hr>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <UserDetail></UserDetail>
      </v-flex>
      <v-flex xs12 sm6>
        <UserEdit></UserEdit>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import UserDetail from './UserDetail.vue'
import UserEdit from './UserEdit.vue'

export default {
  components: {
    UserDetail,
    UserEdit
  }
}
</script>

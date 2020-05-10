<template>
  <div class="red lighten-3 pa-3">
    <h3>자세한 회원 정보를 확인합니다.</h3>
    <p>{{ nameOfChild }}</p>
    <p>{{ sayHello }}</p>
    <v-btn
        depressed
        small
        color="primary"
        @click="switchName"
    >
        이름 변경
    </v-btn>
  </div>
</template>
<script>
export default {
  props: {
    nameOfChild: {
      type: String,
      default: 'hi',
      required: true
    }
  },
  data () {
    return {
      age: 30
    }
  },
  computed: {
    sayHello () {
      return this.nameOfChild + ' 내이름은 xxx'
    }
  },
  methods: {
    switchName () {
      this.nameOfChild = '컴퓨터 '
    }
  }
}
</script>

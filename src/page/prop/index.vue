<template>
  <div>
    {{JSON.stringify(pobj)}}
    <Child :obj="pobj" @updateObj="updateObj" >

    </Child>
  </div>
</template>

<script>
import Child from './child'
export default {
  components: {
    Child,
  },
  data() {
    return {
      pobj: []
    }
  },
  methods: {
    updateObj(data) {
      // this.pobj = JSON.parse(JSON.stringify(data))
      // this.pobj = data
      // this.$set(this.pobj, data)
      this.pobj = Object.assign([], data)
    }
  }
}
</script>

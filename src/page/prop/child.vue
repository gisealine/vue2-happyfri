<template>
  <div>

    <div>
      <button type="button" @click="changeData">按钮</button>

    </div>
    <div>
      {{JSON.stringify(obj)}}
    </div>
<!--    <div>
      {{obj[1].children[0].label}}
    </div>-->

  </div>
</template>

<script>
export default {
  props: ['obj'],
  data() {
    return {

    }
  },
  mounted() {

  },
  methods: {
    changeData() {
      // this.$set(this.obj, 1, 'abc')
      // let newObj = Object.assign([], this.obj)
      // this.obj = [1, 2]
      this.obj = [
        {
          label: 'outter 01',
          children: [
            {
              label: 'inner 01'
            },
            {
              label: 'inner 01'
            }
          ]
        },
        {
          label: 'outter 02',
          children: [
            {
              label: 'inner 01'
            },
            {
              label: 'inner 01'
            }
          ]
        }
      ]
      this.obj[1].children[0] = {a: 'aaaa'}
      this.$emit('updateObj', this.obj)
    }
  }

}
</script>

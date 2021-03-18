<template>
	<div class="input">
    <label>
      <slot></slot>
    </label>
    <input
      v-model="val"
			:type="type"
			:placeholder="placeholder"
			:class="`${type}__input`"
			:min="isNumber"
    >
  </div>
</template>

<script>
	export default {
		props: {
			type: {
				type: String,
				default: 'text'
			},
			value: {
				type: [String, Number],
				required: false,
				default: '',
			},
			placeholder: {
				type: String,
				required: false,
				default: '',
			},
		},
		data() {
			return {
				val: ''
			}
		},
		created () {
			return	this.value ? this.val = this.value : this.val
		},
		watch: {
    val (newValue, oldValue) {
      if (newValue !== oldValue) {
        this.$emit('input', newValue)
      }
    },
    value (newValue, oldValue) {
      if (newValue !== oldValue) {
        this.val = newValue
      }
    },
  },
		computed: {
			isNumber() {
				return this.type === 'number' ? '10' : '' 
			}
		},
	}
</script>

<style lang="scss" scoped>

</style>
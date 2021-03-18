<template>
  <div class="card__list">
    <div class="title">
      {{ title }}
    </div>
    <div class="body">
      {{ body }}
    </div>
    <div class="img">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
	props: {
		title: {
			type: String,
			default: '',
		},
		body: {
			type: String,
			default: '',
		},
	},
};
</script>

<style lang="scss" scoped></style>

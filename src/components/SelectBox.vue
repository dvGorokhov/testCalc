<template>
  <div class="wrapper-dropdown-1" @click="getActive">
    <span class="show"><slot>{{item}}</slot></span>
    <ul class="dropdown">
      <li 
				v-for="list in lists"
				:key="list.id"
				@click="isLi($event, list)"
				>{{ list.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
	props: {
		lists: {
			type: Array,
			default: () => [],
		},
	},
	data() {
		return {
			item: ''
		}
	},
	mounted () {
		this.item = this.lists[0].name
	},
	methods: {
		getActive (e) {
				let target = e.target
				let el = document.querySelectorAll('.wrapper-dropdown-1')
				if (target.tagName == "SPAN") {
					target = e.target.parentNode
				}
				el.forEach(element => {
					if (element === target) {
					element.classList.toggle('active');
					target.firstChild.classList.toggle('hide')
				}
			});
		},
		isLi (e, list) {
			this.item = e.target.textContent
			e.target.parentNode.parentNode.classList.toggle('active')
			e.target.parentNode.parentNode.firstChild.classList.toggle('hide')
			this.$emit('click',list)
		}
	},
};
</script>

<style lang="scss" scoped>
	.wrapper-dropdown-1 {
		position: relative;
		width: 301px;
		height: 49px;
		margin: 0 auto;
		padding: 15px 15px 0 28px;
		margin-top: 0.5rem;
		cursor: pointer;
		outline: none;
		border-radius: 38px;
		box-shadow: 0px 4px 14px rgba(0, 0, 0, 0.07);
	}
	span::after {
		content: "";
		position: absolute;
		width: 0;
		height: 0;
		position: absolute;
		right: 16px;
		top: 45%;
		margin-top: -3px;
		border: solid black;
		border-width: 0 3px 3px 0;
		display: inline-block;
		padding: 3px;
		transform: rotate(45deg);
		-webkit-transform: rotate(45deg);
	}
	.dropdown {
		border-bottom-left-radius: 26px;
		border-bottom-right-radius: 26px;
		text-align: center;
		padding: 0;
	}
	.wrapper-dropdown-1 .dropdown {
		position: absolute;
		top: 27px;
		left: 0px;
		right: 0px;
		background: white;
		transition: all 0.3s ease-out;
		list-style: none;
		opacity: 0;
		pointer-events: none;
	}
	.wrapper-dropdown-1 .dropdown li {
		display: block;
		text-decoration: none;
		color: #333;
		padding: 10px;
		transition: all 0.3s ease-out;
	} 
	.wrapper-dropdown-1 .dropdown li  {
		margin-right: 5px;
		color: inherit;
		vertical-align: middle;
	}
	.wrapper-dropdown-1 .dropdown li:hover  {
		color: grey;
	}
	.wrapper-dropdown-1.active span::after {
		border: solid #00BC35;
		border-width: 0 3px 3px 0;
		transform: rotate(-135deg);
		-webkit-transform: rotate(-135deg);
	}
	.wrapper-dropdown-1.active .dropdown {
		box-shadow: 0px 2px 0px rgb(0 0 0 / 7%);
		opacity: 1;
		pointer-events: auto;
		z-index: 9;
	}
	.hide {
		font-size: 0;
	}
</style>

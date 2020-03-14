<template lang="html">

	<section class="list-sorting">
		<div :id="cid" @click="sortingList()">Sort List</div>
		<ul :id="id">
			<li v-for="data in dataList" :key="id">{{data.id + ". "}}{{data.name}}</li>
		</ul> 
	</section>

</template>

<script lang="js">

	export default {
		name: 'ListSorting',
		props: {
			dataList: {
				type: Array
			},
			id: {
				type: String
			},
			cid: {
				type: String
			}
		},
		mounted () {

		},
		data () {
			return {

			}
		},
		methods: {
			sortingList: function(){
				var list, 
				i, 
				switchStatus, 
				element, 
				shouldSwitch, 
				direction, 
				switchcount = 0;

				list = document.getElementById(this.id);
				switchStatus = true;

				direction = "asc"; 

				while (switchStatus) {

					switchStatus = false;
					element = list.getElementsByTagName("LI");

					for (i = 0; i < (element.length - 1); i++) {

						shouldSwitch = false;

						if (direction == "asc") {

							if (element[i].innerHTML.toLowerCase() > element[i + 1].innerHTML.toLowerCase()) {

								shouldSwitch = true;
								break;

							}

						} else if (direction == "desc") {

							if (element[i].innerHTML.toLowerCase() < element[i + 1].innerHTML.toLowerCase()) {

								shouldSwitch= true;
								break;

								}

							}

						}

					if (shouldSwitch) {

						element[i].parentNode.insertBefore(element[i + 1], element[i]);
						switchStatus = true;
						switchcount ++;

					} else {

						if (switchcount == 0 && direction == "asc") {

							direction = "desc";
							switchStatus = true;

						}

					}

				}

			}
		},
		computed: {

		}
}


</script>

<style scoped lang="scss">
	.list-sorting {

	}
</style>

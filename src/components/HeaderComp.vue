<template>
	<header>
		<!-- Colonna di sinistra -->
		<div class="colLeft">
			<img
				src="https://image.tmdb.org/t/p/original/wwemzKWzjKYJFfCeiB57q3r4Bcm.svg"
				alt=""
			/>

			<span>Home</span>
			<span>Serie TV</span>
			<span>Film</span>
			<span>Nuovi e popolari</span>
			<span>La mia lista</span>
			<span>Sfoglia per lingua</span>
		</div>

		<!-- Colonna di Destra Ricerca -->
		<div class="colRight">
			<!-- Search -->
			<div class="btn-group dropstart search">
				<font-awesome-icon
					icon="fa-solid fa-magnifying-glass dropdown-toggle"
					data-bs-toggle="dropdown"
					aria-expanded="false"
				/>

				<input
					v-model="querySearch"
					type="text"
					class="dropdown-menu"
					placeholder="Cerca il tuo Film-Serie"
				/>
			</div>

			<!-- Lingua -->
			<select class="select" v-model="sceltaLingua">
				<option value="" disabled selected class="selezione">
					Lingua
				</option>
				<option
					v-for="(elem, index) in propsLingue"
					:key="index"
					:value="elem.iso_639_1"
				>
					{{ elem.english_name }}
				</option>
			</select>

			<!-- Genere -->
			<select class="select" v-model="sceltaGenere">
				<option value="" disabled selected class="selezione">
					Genere
				</option>
				<option
					v-for="(elem, index) in propsGeneri"
					:key="index"
					:value="elem.id"
				>
					{{ elem.name }}
				</option>
			</select>

			<!-- DropDown USERS -->
			<div class="dropdown">
				<!-- Bottone Attiva DropDown USERS-->
				<div class="containerUser">
					<div class="contUsersIcona">
						<font-awesome-icon
							class="dropbtn"
							icon="fa-solid fa-circle-user"
						/>
					</div>

					<font-awesome-icon icon="fa-solid fa-caret-down" />
					<font-awesome-icon icon="fa-solid fa-sort-up" />
				</div>

				<!-- Contenuto DropDown -->
				<div class="dropdown-content">
					<div>
						<a href=""
							><font-awesome-icon
								class="icona"
								icon="fa-solid fa-circle-user"
							/>Users</a
						>
						<a href="#">
							<font-awesome-icon
								class="icona"
								icon="fa-solid fa-pen-to-square"
							/>Gestisci Profili</a
						>
						<a href="#">
							<font-awesome-icon
								class="icona"
								icon="fa-solid fa-user-large"
							/>Account</a
						>
						<a href="#">
							<font-awesome-icon
								class="icona"
								icon="fa-solid fa-question"
							/>
							Centro Assistenza</a
						>
					</div>
					<div class="disconetti">
						<a href="#">Esci da Netflix</a>
					</div>
				</div>
			</div>
		</div>
	</header>
</template>

<script>
export default {
	name: "HeaderComp",
	components: {},
	props: {
		propsGeneri: Array,
		propsLingue: Array,
	},
	data() {
		return {
			querySearch: "",
			sceltaGenere: "",
			sceltaLingua: "",
		};
	},
	updated() {
		this.$emit("emitQuery", this.querySearch);
		this.$emit("emitGenere", this.sceltaGenere);
		this.$emit("emitLingua", this.sceltaLingua);
	},
};
</script>

<style lang="scss" scoped>
@import "./MIXIN/mixinHeader.scss";
header {
	height: 10vh;
	background: rgb(80, 80, 80);
	background: linear-gradient(
		0deg,
		rgba(80, 80, 80, 1) 0%,
		rgba(0, 0, 0, 1) 100%
	);
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 20px;
	@include headerMixin;
}
</style>
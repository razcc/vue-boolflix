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
					type="text"
					class="dropdown-menu"
					placeholder="Cerca il tuo Film-Serie"
				/>
			</div>

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
	data() {
		return {};
	},
};
</script>

<style lang="scss" scoped>
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
}

// Col Left Logo
.colLeft {
	height: 100%;
	display: flex;
	align-items: center;
}
img {
	height: 50%;
}

.colLeft span{
    color: white;
    font-size: 20px;
    margin: 25px;
}
.colLeft span:hover{
    cursor: pointer;
    color: rgba(255,3,0,0.8);
}

// Col right Search
.colRight {
	display: flex;
	align-items: center;
	margin-right: 50px;
}

// Bottone Ricerca
.fa-magnifying-glass {
	color: white;
	font-size: 30px;
	margin-right: 50px;
	margin-left: 50px;
}
// DropDown Ricerca
.dropdown-menu {
	min-width: 20rem;
	border-color: red;
}

// Bottone Users
.containerUser {
	display: flex;
	align-items: center;
	gap: 10px;
}
.contUsersIcona {
	border: 2px solid white;
	border-radius: 10px;
	padding: 5px;
	background: rgb(99, 1, 0);
	background: linear-gradient(
		0deg,
		rgba(99, 1, 0, 1) 0%,
		rgba(231, 97, 97, 1) 100%
	);
}
.dropbtn {
	color: white;
	font-size: 60px;
}
.containerUser:hover .dropbtn {
	color: rgba(99, 1, 0, 1);
}
.fa-sort-up {
	color: white;
	display: none;
}
.fa-caret-down {
	color: white;
}
.containerUser:hover .fa-caret-down {
	color: red;
	display: none;
}
.containerUser:hover .fa-sort-up {
	display: block;
}

// DropDown Users
.dropdown-content {
	display: none;
	position: absolute;
	left: -300%;
	background-color: rgba(0, 0, 0, 0.6);
	min-width: 220px;
	box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
	z-index: 1;
}

.dropdown-content a {
	color: white;
	padding: 12px 16px;
	font-size: 20px;
	text-decoration: none;
	display: block;
}

.dropdown:hover .dropdown-content {
	display: block;
}
.disconetti {
	border-top: 2px solid white;
	display: flex;
	justify-content: center;
}
.icona {
	margin-right: 20px;
}
</style>
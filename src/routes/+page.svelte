<script lang="ts">
	import { redirect } from '@sveltejs/kit';
    import axios from "axios"
	let username: string = '';

	const setUsername = (e: any) => {
		e.target.value ? (username = e.target.value) : (username = '');
	};

    const checkUsername = async (username: string) => {
        const usernameObject = {
            "username": username
        }
        const res = await axios.post("http://localhost:5133/user", usernameObject)


        // const res = await axios.get("http://localhost:5133/get-random-question")

        console.log(res)

    }

	function logIn() {
		console.log(username);
	}
</script>

<head>
	<title>Username Login</title>
</head>

<body>
	<div class="bg-text">
		<input
			type="text"
			id="username"
			placeholder="username"
			on:input={(e) => setUsername(e)}
			value={username}
		/>
		<a href={username.length > 0 ? '/home-page' : '/'}>
			<button on:click={checkUsername(username)} disabled={username.length === 0} on:click={logIn}>login</button>
		</a>
	</div>
</body>

<style>
	body {
		background-color: #fbb900;
	}

	.bg-text {
		background-color: rgb(0, 0, 0); /* Fallback color */
		background-color: rgba(255, 255, 255, 0.7); /* Black w/opacity/see-through */
		color: black;
		font-size: 80px;
		border: 10px solid black;
		position: fixed;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 225px;
		padding: 225px;
		text-align: center;
	}
</style>

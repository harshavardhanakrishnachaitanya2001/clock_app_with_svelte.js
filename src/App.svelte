<style>
	h1,h2{
		text-align: center;
		margin-top: 0px;
	}
	h1{
		font-size: 5rem;
		margin-bottom: 0px;
		margin-top: 0px;
		border: 1px solid black;
		border-right: 0px;
		border-left: 0px;
		color:burlywood;
		background:black;
	}
	h2{
		font-size: 2rem;
		margin-bottom: 0px;
		margin-top: 15px;
	}
	h3{
		text-align: center;
		font-size:4rem;
		margin-top:4rem;
	}

	img{
		height:5rem;
		width: 5rem;
		margin-left: 1rem;
	}
	label{
		text-align: center;
		margin-top: 25px;
	}
	button{
		cursor:pointer;
	}
</style>
<script>
	let usersHours=12;
	let usersMinutes=0;
	let setHours=12;
	let setMinutes=0;
	let seconds=0;
	setInterval(() => {	
		seconds++;
		seconds=seconds;
		if(seconds===60){
		setMinutes++;
		seconds=0;
	}
	if(setMinutes===60&& setHours!=12){
		seconds=0;
		setMinutes=0;
		setHours+=1;
	}
	if (setHours===12 && setMinutes===60){
		setHours=1;
		setMinutes=0;
		seconds=0;
	}
	}, 1000);
	function handleHoursChange(e){
		e.preventDefault();
		usersHours-e.target.value;
	};
	function handleMinutesChange(event){
		e.preventDefault();
		usersMinutes=event.target.value;
	};
	function handleClick(){
		setHours=usersHours;
		setMinutes=usersMinutes;
		usersHours='';
		usersMinutes='';
	};
</script>
<h1>
	Clock with svelte
	<img src='images/icon.jfif' alt="clockImage"/>
</h1>
<div>
	<h2>Developed by G. Harshavardhana Krishna Chaitanya</h2>
	<label>
		<b>Hours:</b> <input type='number' on:change={handleHoursChange} bind:value={usersHours}/>
		<b>Minutes:</b> <input type='number' on:change={handleMinutesChange} bind:value={usersMinutes}/>
		<button on:click={handleClick}>Set</button>
	</label>
	<h3>Time of day: {setHours}:{setMinutes}:{seconds}</h3>
</div>
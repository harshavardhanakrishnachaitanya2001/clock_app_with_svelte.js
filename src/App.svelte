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
	}
	h3{
		text-align: center;
		font-size:4rem;
		margin-top: 5px;
	}

	img{
		height:5rem;
		width: 5rem;
		margin-left: 1rem;
	}
</style>
<script>
	let hours=12;
	let minutes=0;
	let seconds=0;
	let i=1;
	let amorpm='a.m.'
	setInterval(() => {	
		seconds++;
		seconds=seconds;
		if(seconds===60){
		minutes++;
		seconds=0;
	}
	if(minutes===60&& hours!=12){
		seconds=0;
		minutes=0;
		hours+=1;
		i++;
	}
	if (hours===12 && minutes===60){
		hours=1;
		minutes=0;
		seconds=0;
	}
	if(i===12){
		amorpm='p.m.';
	}
	}, 1000);
	let usersHours='';
	let usersMinutes='';
	let setHours;
	let setMinutes;
	function handleHoursChange(e){
		e.preventDefault();
		usersHours-e.target.value;
	};
	function handleMinutesChange(e){
		e.preventDefault();
		usersMinutes=e.target.data;
	};
	function handleClick(){
		setHours=usersHours;
		setMinutes=usersMinutes;
	};
</script>
<h1>
	Clock with svelte
	<img src='images/icon.jfif' alt="clockImage"/>
</h1>
<div>
	<h2>Developed by G. Harshavardhana Krishna Chaitanya</h2>
	<h3>Time of day: {hours}:{minutes}:{seconds}{amorpm}</h3>
	<input type='number' on:change={handleHoursChange} value={usersHours}/>
	<input type='number' on:change={handleMinutesChange} data={usersMinutes}/>
	<button on:click={handleClick}>Set</button>


	<p>{setMinutes}	{setMinutes}</p>
</div>
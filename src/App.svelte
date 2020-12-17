<style>
	h1,h2{
		text-align: center;
		margin-top: 0px;
	}
	h1{
		font-size: 4rem;
		margin-bottom: 5px;
	}
	h2{
		font-weight: 2rem;
		margin-bottom: 0px;
	}
	h3{
		text-align: center;
		font-size:3rem;
	}
</style>
<script>
	let hours=12;
	let minutes=0;
	let seconds=0;
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
	}
	if (hours===12 && minutes===60){
		hours=1;
		minutes=0;
		seconds=0;
	}
	}, 1000);

</script>
<div>
	<h1>Clock with svelte</h1>
	<h2>Developed by G. Harshavardhana Krishna Chaitanya</h2>
	<h3>Time of day: {hours}:{minutes}:{seconds}</h3>
</div>
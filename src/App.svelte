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
</script>
<div>
	<h1>Clock with svelte</h1>
	<h2>Developed by G. Harshavardhana Krishna Chaitanya</h2>
	<h3>Time of day: {hours}:{minutes}:{seconds}{amorpm}</h3>
</div>
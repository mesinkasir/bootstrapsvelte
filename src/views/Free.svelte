<script>
	import Navbar from "../widget/Navbar.svelte";	import { onMount } from 'svelte';
    let count = 1;

$: doubled = count * 1;
$: quadrupled = doubled * 2;

function handleClick() {
    count += 1;
}
    let people = [
		{ first: 'Messi', last: 'Leo' },
		{ first: 'Cristiano', last: 'Ronaldo' },
		{ first: 'Cornor', last: 'Mcgregor' }
	];

	let prefix = '';
	let first = '';
	let last = '';
	let i = 0;

	$: filteredPeople = prefix
		? people.filter(person => {
			const name = `${person.last}, ${person.first}`;
			return name.toLowerCase().startsWith(prefix.toLowerCase());
		})
		: people;

	$: selected = filteredPeople[i];

	$: reset_inputs(selected);

	function create() {
		people = people.concat({ first, last });
		i = people.length - 1;
		first = last = '';
	}

	function update() {
		selected.first = first;
		selected.last = last;
		people = people;
	}

	function remove() {
		// Remove selected person from the source array (people), not the filtered array
		const index = people.indexOf(selected);
		people = [...people.slice(0, index), ...people.slice(index + 1)];

		first = last = '';
		i = Math.min(i, filteredPeople.length - 2);
	}

	function reset_inputs(person) {
		first = person ? person.first : '';
		last = person ? person.last : '';
	}

let time = new Date();

$: hours = time.getHours();
$: minutes = time.getMinutes();
$: seconds = time.getSeconds();

onMount(() => {
    const interval = setInterval(() => {
        time = new Date();
    }, 1000);

    return () => {
        clearInterval(interval);
    };
});
  </script>
  <main>
    <Navbar/>
    <div class="row">
        <div class="col-12 p-3 p-md-5 text-center">
            <h3><strong>Taste a freedom</strong></h3>
        </div>
        
        <div class="col-md-4 p-3 p-md-5 text-center border border-light">
            
<button on:click={handleClick}>
	Count: {count}
</button>

<p>{count} * 2 = {doubled}</p>
<p>{doubled} * 2 = {quadrupled}</p>
        </div>
        <div class="col-md-4 p-3 p-md-5 text-center border border-light">
            
<input placeholder="filter prefix" bind:value={prefix}>

<select bind:value={i} size={5}>
	{#each filteredPeople as person, i}
		<option value={i}>{person.last}, {person.first}</option>
	{/each}
</select>

<label><input bind:value={first} placeholder="first"></label>
<label><input bind:value={last} placeholder="last"></label>

<div class='buttons'>
	<button on:click={create} disabled="{!first || !last}">create</button>
	<button on:click={update} disabled="{!first || !last || !selected}">update</button>
	<button on:click={remove} disabled="{!selected}">delete</button>
</div>

<style>
	* {
		font-family: inherit;
		font-size: inherit;
	}

	input {
		display: block;
		margin: 0 0 0.5em 0;
	}

	select {
		float: left;
		margin: 0 1em 1em 0;
		width: 14em;
	}

	.buttons {
		clear: both;
	}
</style>
        </div>
        <div class="col-md-4 p-3 p-md-5 text-center border border-light">
            <svg viewBox='-50 -50 100 100'>
                <circle class='clock-face' r='48'/>
            
                <!-- markers -->
                {#each [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55] as minute}
                    <line
                        class='major'
                        y1='35'
                        y2='45'
                        transform='rotate({30 * minute})'
                    />
            
                    {#each [1, 2, 3, 4] as offset}
                        <line
                            class='minor'
                            y1='42'
                            y2='45'
                            transform='rotate({6 * (minute + offset)})'
                        />
                    {/each}
                {/each}
            
                <!-- hour hand -->
                <line
                    class='hour'
                    y1='2'
                    y2='-20'
                    transform='rotate({30 * hours + minutes / 2})'
                />
            
                <!-- minute hand -->
                <line
                    class='minute'
                    y1='4'
                    y2='-30'
                    transform='rotate({6 * minutes + seconds / 10})'
                />
            
                <!-- second hand -->
                <g transform='rotate({6 * seconds})'>
                    <line class='second' y1='10' y2='-38'/>
                    <line class='second-counterweight' y1='10' y2='2'/>
                </g>
            </svg>
            
            <style>
                svg {
                    width: 100%;
                    height: 100%;
                }
            
                .clock-face {
                    stroke: #333;
                    fill: white;
                }
            
                .minor {
                    stroke: #999;
                    stroke-width: 0.5;
                }
            
                .major {
                    stroke: #333;
                    stroke-width: 1;
                }
            
                .hour {
                    stroke: #333;
                }
            
                .minute {
                    stroke: #666;
                }
            
                .second, .second-counterweight {
                    stroke: rgb(180,0,0);
                }
            
                .second-counterweight {
                    stroke-width: 3;
                }
            </style>
        </div>
    <div class="col-12 col-md-7 p-0"> 
    <img class="img-fluid" alt="bootstrap svelte" width="100%" src="https://1.bp.blogspot.com/-3KL513KxczE/YW_zuHAK8nI/AAAAAAAARY0/yolbrzTauJI4qy1EkGIs-_ou3jWQnLx6wCLcBGAsYHQ/s740/ratm.jpg"/>
    </div>
        <div class="col-12 col-md-5 p-3 bg-light">
    <p>
        The movie ran through me
- The glamour subdue me
- The tabloid untie me
- I'm empty please fill me
- mister anchor assure me
- That Baghdad is burning
- Your voice it is so soothing
- That cunning mantra of killing
- I need you my witness
- To dress this up so bloodless
- To numb me and purge me now
- Of thoughts of blaming you
- Yes the car is our wheelchair
- My witness your coughing
- Oily silence mocks the legless
- Now traveling in coffins
- But on the corner
- The jury's sleepless
- We found your weakness
- And it's right outside our door
- Now testify
- With precision you feed me
- My witness I'm hungry
- Your temple it calms me
- So I can carry on
- My slaving sweating the skin right off my bones
- On a bed of fire I'm choking on the smoke that
- fills my home
- The wrecking ball rushing
- My witness your blushing
- The pipeline is gushing
- While here we lie in tombs
- While on the corner
- The jury's sleepless
- We found your weakness
- And it's right outside your door
- Now testify
- Mass graves for the pump and the price is set
- Who controls the past now controls the future
- Who controls the present now controls the past
- Who controls the past now controls the future
- Who controls the present now?
- Now testify
</p>
</div>
</div>
</main>
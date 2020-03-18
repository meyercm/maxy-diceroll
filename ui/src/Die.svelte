<script>
	import _ from 'lodash'
  export let sides;
	
	const randomRoll = (max) => 1 + Math.floor(Math.random() * Math.floor(max));
	
	let history = [];
	const reroll = () => {
    const nextValue = randomRoll(sides);
    history = [...history, nextValue];
  }
	$: historyString = _.join(history, ',');
	
</script>

<style>
.die {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  grid-template-rows: auto /*repeat(2, 1fr)*/;
}

.rollButton {
  grid-column: 3 / 6;
  grid-row: 1;
  padding: 1em;
  font-size: larger;
}

.historyText {
  grid-column: 1 / 7;
  grid-row: 2;
  justify-self: start;
  font-size: larger;
  word-wrap: break-word;
  word-break: break-all;
  max-width: 100%;
}

.clearButton {
  grid-column: 7;
  grid-row: 2;
  align-self: center;
  padding: 0.5em;
}

</style>

<div class="die">
	
	<button class="rollButton" on:click={ reroll }>Roll d{ sides }</button>
  <button class="clearButton" on:click={ () => history = [] }>X</button>
  <h3 class="historyText">{ historyString }</h3>
  
</div>
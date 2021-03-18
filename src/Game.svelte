<script lang="ts">
    import {GameController} from "./game";
    import Pipe from './Pipe.svelte'
    const game= new GameController();
    let frame= game.newGame();

    setInterval(() => {
      frame = game.nextFrame();
    }, 1000/ 90);
</script>

<style>
  main{
      position: relative;
      border: solid black 1px;
      overflow:hidden;
      background-color: lightblue;
  }
</style>

<main
  style="width:{frame.width}px; height: {frame.height}px;"
  class= "game"
>
<Pipe pipe="{frame.firstPipe}" />
<Pipe pipe="{frame.secondPipe}" /> 
</main>
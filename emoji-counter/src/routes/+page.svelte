<script>
  import happy from "../assets/emojis/happy.png";
  import sad from "../assets/emojis/sad.png";
  import angry from "../assets/emojis/angry.png";

  let emojis = [
    { id: 0, name: "Happy", color: "green", count: 0, src: happy },
    { id: 1, name: "Sad", color: "blue", count: 0, src: sad },
    { id: 2, name: "Angry", color: "red", count: 0, src: angry },
  ];

  $: totalCount = emojis[0].count + emojis[1].count + emojis[2].count;
  //   $: totalCount = emojis.reduce((total, emoji) => total + emoji.count, 0

  function handleClick(emoji) {
    emojis[emoji.id].count++;
  }
</script>

<h1>Welcome to Svelte</h1>
<p class="mainText">How are we feeling today?</p>
<div class="wrapper">
  <!-- {#each emojis as {id, name, color, count}, index (id)} -->
  {#each emojis as emoji}
    {@const count = emoji.count}
    {@const name = emoji.name}
    <div class="emojiButton">
      <img class="emojiImg" src={emoji.src} alt="name" />
      <button class={emoji.color} on:click={() => handleClick(emoji)}>
        {emoji.name} - clicked {count} {count === 1 ? "time" : "times"}</button
      >
    </div>
  {/each}
</div>
<p>Total Emotions = {totalCount}</p>

<style>
  .wrapper {
    margin: 2rem auto;
    width: 75%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .emojiButton {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
  }

  .emojiImg {
    width: 7rem;
    margin-bottom: 3rem;
  }
  button {
    padding: 0.5rem 1rem;
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
  }

  p {
    text-align: center;
    font-size: 1.5rem;
  }

  .mainText {
    font-size: 2rem;
  }
  .red {
    background-color: red;
  }

  .green {
    background-color: green;
  }

  .blue {
    background-color: blue;
  }
  .reset {
    background-color: black;
    display: block;
    margin: 0 auto;
  }
</style>

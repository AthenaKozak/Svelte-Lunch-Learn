<script>
  import happy from "../assets/emojis/happy.png";
  import sad from "../assets/emojis/sad.png";
  import angry from "../assets/emojis/angry.png";

  let emojis = [
    { id: 0, name: "Happy", color: "green", count: 0, src: happy },
    { id: 1, name: "Sad", color: "blue", count: 0, src: sad },
    { id: 2, name: "Angry", color: "red", count: 0, src: angry },
  ];
</script>

<h1>Welcome to Svelte</h1>
<p>Emoji Counter goes here!</p>

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

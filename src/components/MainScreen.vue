<template>
  <div class="screen">
    <h1>POKEMON MEMORIOS</h1>
    <h3>Selec mode to start game</h3>
    <div class="actions">
      <button class="buttons" @click="onStart(16)">
        <span>4x4</span>
        <span>Easy</span>
      </button>
      <button class="buttons" @click="onStart(36)">
        <span>6x6</span>
        <span>Nomal</span>
      </button>
      <button class="buttons" @click="onStart(64)">
        <span>8x8</span>
        <span>Hard</span>
      </button>
      <button class="buttons" @click="onStart(100)">
        <span>10x10</span>
        <span>Supper Hard</span>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    onStart(totalOfBlocks) {
      this.$emit("onStart", { totalOfBlocks });
    },
  },
};
</script>
<style lang="css" scoped>
.screen {
  width: 100%;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 2;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  background-color: black;
  color: var(--light);
}

.screen h1 {
  font-size: 4.5rem;
  text-transform: uppercase;
}

.screen p {
  font-size: 2rem;
}

.modes {
  display: flex;
  margin-top: 2rem;
}

.modes button {
  font: var(--font);
  width: 150px;
  height: 150px;
  background: transparent;
  box-shadow: none;
  border: 1px solid var(--light);
  color: var(--light);
  display: flex;
  flex-direction: column;
  border-radius: 1rem;
  margin: 0 1rem;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.3s ease-in-out;
}

.modes button:hover {
  background-color: var(--light);
  color: var(--dark);
}

.modes button span:first-child {
  font-size: 2rem;
}

.modes button span:last-child {
  display: block;
  font-size: 1.25rem;
  margin-top: 0.5rem;
}
.buttons {
  display: inline-block;
  padding: 15px 25px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #fff;
  background-color: #4caf50;
  border: none;
  border-radius: 40px/40px;
  box-shadow: 0 9px #850808;
}

.buttons:hover {
  background-color: #3e8e41;
}

.buttons:active {
  background-color: #3e8e41;
  box-shadow: 0 5px #7e0606;
  transform: translateY(4px);
}
</style>

<template>
  <div class="looping-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <h5>Looping over an Array</h5>
          <p>
            Use the v-for directive to loop over the "players" property on the
            components data. In the curlies inside of the template for each
            player we want to access each property on the player object to put
            the value into our html.
          </p>
          <p>
            Then use the index to print the players place in the collection.
          </p>
          <!-- add the v-for to player-card -->
          <div class="player-card text-center" v-for="player in state.players">
            <h5>Player Cards</h5>
            <div>
              <img class="img" :src="player.photo" />
            </div>
            <div>
              <span>{{ player.name }}</span>
            </div>
            <div>
              <span>{{ player.position }}</span>
            </div>
            <div>
              <span>{{ player.number }}</span>
            </div>
          </div>
        </div>
        <div class="border p-1">
          <h5>Looping over an Objects Properties</h5>
          <p>
            Use the v-for directive to loop over the "blog" property on the
            comments data. In the curlies inside of the template for each
            property on the object we want to print the key(property name) and
            value contained at that key.
          </p>
          <div class="blog" v-for="(value, key) in state.blog" :key="key">
            <p>{{ key }}: {{ value }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { reactive } from "vue";
export default {
  name: "looping-exercise",
  setup() {
    // NOTE typically state will be abstracted to a global AppState
    const state = reactive({
      blog: {
        title: "Using v-for in Vue",
        description: "How to use a v-for directive in Vue.",
        author: "Mick",
      },
      players: [
        {
          photo: "https://robohash.org/Mick",
          name: "Mick",
          position: "WR",
          number: 4,
        },
        {
          photo: "https://robohash.org/Jeremy",
          name: "Jeremy",
          position: "TE",
          number: 13,
        },
        {
          photo: "https://robohash.org/Jake",
          name: "Jake",
          position: "QB",
          number: 1,
        },
      ],
    });
    return {
      state,
    };
  },
};
</script>


<style scoped>
.player-card {
  border: 1px solid rgba(154, 154, 156, 0.4);
  background-color: rgba(154, 154, 156, 0.4);
  margin: 1rem;
  border-radius: 5px;
}

.img {
  height: 10rem;
}
</style>
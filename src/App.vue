<template>
  <div id="app">
    <label>Simple Omnibox (type: 'cat' or 'serious'):</label>
    <omnibox class="box" :options="options" />
    <label>Omnibox with scoped slots (type: 'cat' or 'serious'):</label>
    <omnibox
      class="box"
      :options="options">
      <template v-slot:option="{ option }">
        <img :src="option.img" class="thumbnail"><div class="label">{{ option.label }}</div>
      </template>
    </omnibox>
  </div>
</template>

<script>
import Omnibox from 'vue-omnibox/src/Omnibox'

export default {
  name: 'App',
  components: {
    Omnibox,
  },
  data () {
    return {
      options: [
      {
        id: 1,
        label: "cat",
        img: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Feral_cat_Virginia_crop.jpg/800px-Feral_cat_Virginia_crop.jpg'
      },
      {
        id: 2,
        label: "cat two",
        img: 'https://upload.wikimedia.org/wikipedia/commons/thumb/4/4f/Felis_silvestris_catus_lying_on_rice_straw.jpg/1920px-Felis_silvestris_catus_lying_on_rice_straw.jpg'
      },
      {
        id: 3,
        label: "cat three",
        img: 'https://upload.wikimedia.org/wikipedia/commons/thumb/f/f3/Youngkitten.JPG/1280px-Youngkitten.JPG'
      },
      {
        id: 4,
        label: "cat four",
        img: 'https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Juvenile_Ragdoll.jpg/1280px-Juvenile_Ragdoll.jpg'
      },
      {
        id: 5,
        label: "serious cat",
        img: 'https://upload.wikimedia.org/wikipedia/commons/4/44/CatLolCatExample.jpg'
      },
    ]
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.thumbnail {
  max-height: 200px;
  margin-top: 10px;
  margin-bottom: 10px;
}
.label {
  height: 200px;
  vertical-align: middle;
  display: inline-block;
  padding-left: 10px;
  font-weight: 600;
}
.box {
  width: 400px;
  margin-bottom: 30px;
  margin-top: 10px;
}
label {
  font-weight: 500;
}
</style>

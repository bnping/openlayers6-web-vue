<template>
  <div id="mapOL" ref="openlayer"></div>
</template>

<script>
import 'ol/ol.css';
import Map from "ol/Map.js";
import View from "ol/View.js";
import TileLayer from "ol/layer/Tile.js";
import OSM from "ol/source/OSM";

export default {
  data() {
    return {
      map: {}
    };
  },
  mounted() {
    this.map = new Map({
      target: this.$refs.openlayer,
      render: "canvas",
      layers: [new TileLayer({ source: new OSM() })],
      view: new View({
        center: [0, 0],
        zoom: 2
      })
    });
  }
};
</script>


<style lang="stylus">
@import "~ol/ol.css"
#mapOL
  height 700px
</style>


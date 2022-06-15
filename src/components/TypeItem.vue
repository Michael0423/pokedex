<template>
  <div :class="typeClass">{{ typeTxt }}</div>
</template>

<script>
export default {
  name: "TypeItem",
  props: {
    type: String,
  },
  computed: {
    typeClass() {
      let t = "type";
      switch (this.type) {
        case "一般":
          t += " type-normal";
          break;
        case "火":
          t += " type-fire";
          break;
        case "水":
          t += " type-water";
          break;
        case "草":
          t += " type-grass";
          break;
        case "電":
          t += " type-electric";
          break;
        case "冰":
          t += " type-ice";
          break;
        case "格鬥":
          t += " type-fighting";
          break;
        case "毒":
          t += " type-poison";
          break;
        case "地面":
          t += " type-ground";
          break;
        case "飛行":
          t += " type-flying";
          break;
        case "超能力":
          t += " type-psychic";
          break;
        case "蟲":
          t += " type-bug";
          break;
        case "岩石":
          t += " type-rock";
          break;
        case "幽靈":
          t += " type-ghost";
          break;
        case "龍":
          t += " type-dragon";
          break;
        case "惡":
          t += " type-dark";
          break;
        case "鋼":
          t += " type-steel";
          break;
        case "妖精":
          t += " type-fairy";
          break;
        default:
          break;
      }
      return t;
    },
    typeTxt() {
      let t = "";
      switch (this.type) {
        case "":
          break;
        default:
          t = this.type;
          break;
      }
      return t;
    },
  },
};
</script>

<style lang="scss" scoped>
.type {
  border: 1px solid;
  border-radius: 10px;
  margin: 0 5px;
  padding: 3px 5px;

  &-* {
    border: none;
  }
  &-nomal {
    border: 1px solid #000;
    color: white;
  }

  &-fire {
    border-color: #ff6900;
    color: #ff6900;
  }
  &-water {
    border-color: #14b9ff;
    color: #14b9ff;
  }
  &-grass {
    border-color: #b4f000;
    color: #b4f000;
  }
  &-electric {
    border-color: #ffe100;
    color: #ffe100;
  }
  &-ice {
    border-color: #14f5ff;
    color: #14f5ff;
  }
  &-fighting {
    border-color: #dc6900;
    color: #dc6900;
  }
  &-poison {
    border-color: #d28cd2;
    color: #d28cd2;
  }
  &-ground {
    border-color: #fac85a;
    color: #fac85a;
  }
  &-flying {
    border-color: #78dcff;
    color: #78dcff;
  }
  &-psychic {
    border-color: #f08cdc;
    color: #f08cdc;
  }
  &-bug {
    border-color: #46c846;
    color: #46c846;
  }
  &-rock {
    border-color: #b48c64;
    color: #b48c64;
  }
  &-ghost {
    border-color: #a08cff;
    color: #a08cff;
  }
  &-dragon {
    border-color: #5078dc;
    color: #5078dc;
  }
  &-dark {
    border-color: #787878;
    color: #787878;
  }
  &-steel {
    border-color: #aac8f0;
    color: #aac8f0;
  }
  &-fairy {
    border-color: #ffafdc;
    color: #ffafdc;
  }
}
</style>
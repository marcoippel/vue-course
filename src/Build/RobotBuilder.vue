<template>
    <div>
        <div class="top-row">
            <div class="top part">
                <img :src="availableParts.heads[selectedHeadIndex].src" title="head" />
                <button v-on:click="selectNextHead()" class="prev-selector">&#9668;</button>
                <button v-on:click="selectPreviousHead()" class="next-selector">&#9658;</button>
            </div>
        </div>
        <div class="middle-row">
            <div class="left part">
                <img :src="availableParts.arms[selectedLeftArmIndex].src" title="head" />
                <button @click="selectNextLeftArm()" class="prev-selector">&#9650;</button>
                <button @click="selectPreviousLeftArm()" class="next-selector">&#9660;</button>
            </div>
            <div class="center part">
                <img :src="availableParts.torsos[selectedTorsoIndex].src" title="head" />
                <button @click="selectNextTorso()" class="prev-selector">&#9668;</button>
                <button @click="selectPreviousTorso()" class="next-selector">&#9658;</button>
            </div>
            <div class="right part">
                <img :src="availableParts.arms[selectedRightArmIndex].src" title="head" />
                <button @click="selectNextRightArm()" class="prev-selector">&#9650;</button>
                <button @click="selectPreviousRightArm()" class="next-selector">&#9660;</button>
            </div>
        </div>
        <div class="bottom-row">
            <div class="bottom part">
                <img :src="availableParts.bases[selectedBaseIndex].src" title="head" />
                <button @click="selectNextBase()" class="prev-selector">&#9668;</button>
                <button  @click="selectPreviousBase()" class="next-selector">&#9658;</button>
            </div>
        </div>
    </div>
</template>

<script>
import availableParts from '../data/parts';

export default {
  name: 'RobotBuilder',
  data() {
    return {
      availableParts,
      selectedHeadIndex: 0,
      selectedLeftArmIndex: 0,
      selectedTorsoIndex: 0,
      selectedRightArmIndex: 0,
      selectedBaseIndex: 0,

    };
  },
  methods: {
    selectNextHead() {
      this.selectedHeadIndex += 1;
    },
    selectPreviousHead() {
      console.log('selectNextHead');
      this.selectedHeadIndex -= 1;
    },
    selectNextLeftArm() {
      this.selectedLeftArmIndex += 1;
    },
    selectPreviousLeftArm() {
      this.selectedLeftArmIndex -= 1;
    },
    selectNextTorso() {
      this.selectedTorsoIndex += 1;
    },
    selectPreviousTorso() {
      this.selectedTorsoIndex -= 1;
    },
    selectNextRightArm() {
      this.selectedRightArmIndex += 1;
    },
    selectPreviousRightArm() {
      this.selectedRightArmIndex -= 1;
    },
    selectNextBase() {
      this.selectedBaseIndex += 1;
    },
    selectPreviousBase() {
      this.selectedBaseIndex -= 1;
    },

  },
};
</script>

<style>
.part {
    position: relative;
    width: 165px;
    height: 165px;
    border: 3px solid #aaa;
}

.part img {
    width: 165px;
}

.top-row {
    display: flex;
    justify-content: space-around;
}

.middle-row {
    display: flex;
    justify-content: center;
}

.bottom-row {
    display: flex;
    justify-content: space-around;
    border-top: none;
}

.head {
    border-bottom: none;
}

.left {
    border-right: none;
}

.right {
    border-left: none;
}

.left img {
    transform: rotate(-90deg);
}

.right img {
    transform: rotate(90deg);
}

.bottom {
    border-top: none;
}

.prev-selector {
    position: absolute;
    z-index: 1;
    top: -3px;
    left: -28px;
    width: 25px;
    height: 171px;
}

.next-selector {
    position: absolute;
    z-index: 1;
    top: -3px;
    right: -28px;
    width: 25px;
    height: 171px;
}

.center .prev-selector,
.center .next-selector {
    opacity: 0.8;
}

.left .prev-selector {
    top: -28px;
    left: -3px;
    width: 144px;
    height: 25px;
}

.left .next-selector {
    top: auto;
    bottom: -28px;
    left: -3px;
    width: 144px;
    height: 25px;
}

.right .prev-selector {
    top: -28px;
    left: 24px;
    width: 144px;
    height: 25px;
}

.right .next-selector {
    top: auto;
    bottom: -28px;
    left: 24px;
    width: 144px;
    height: 25px;
}

.right .next-selector {
    right: -3px;
}
</style>

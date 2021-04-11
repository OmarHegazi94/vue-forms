<template>
    <!-- <div id="on" @click="isOn = true" :class="{ active: isOn }">
        On
    </div>
    <div id="off" @click="isOn = false" :class="{ active: !isOn }">
        Off
    </div> -->

    <div class="form-check form-switch">
        <input :checked="newValue" @click="switched(newValue)" class="form-check-input" type="checkbox" id="flexSwitchCheckChecked" />
        <label class="form-check-label user-select-none" for="flexSwitchCheckChecked">Checked switch checkbox input</label>
    </div>

</template>

<script>
export default {
    props: ['value'],
    data() {
        return {
            newValue: !this.value
        }
    },
    methods: {
        switched(isOn) {
            // the event has to have the name input 
            // because that is what is V-model is waiting for
            this.$emit('input', isOn)
            // console.log(this.value)
            // console.log(this.newValue)
        }
    }
};
</script>

<style scoped>
#on,
#off {
    width: 40px;
    height: 20px;
    background-color: lightgray;
    padding: 2px;
    display: inline-block;
    margin: 10px -2px;
    box-sizing: border-box;
    cursor: pointer;
    text-align: center;
}

#on:hover,
#on.active {
    background-color: lightgreen;
}

#off:hover,
#off.active {
    background-color: lightcoral;
}
</style>

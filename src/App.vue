<template>
  <div class="container">
    <div class="row">
      <form>
        <h4>Change Border Radius</h4>
        <hr />
        <div class="form-group">
          <label for="radiusTopLeft">Radius Top Left: </label>
          <input
            class="form-control"
            type="text"
            id="radiusTopLeft"
            v-model="radiusTopLeft"
          />

          <label for="radiusTopRight">Radius Top Right: </label>
          <input
            class="form-control"
            type="text"
            id="radiusTopRight"
            v-model="radiusTopRight"
          />

          <label for="radiusBottomRight">Radius Bottom Right: </label>
          <input
            class="form-control"
            type="text"
            id="radiusBottomRight"
            v-model="radiusBottomRight"
          />

          <label for="radiusBottomLeft">Radius Bottom Left: </label>
          <input
            class="form-control"
            type="text"
            id="radiusBottomLeft"
            v-model="radiusBottomLeft"
          />
        </div>
      </form>
    </div>
    <div class="col text">
      <div
        class="d-flex justify text-example-area"
        :style="{
          borderTopLeftRadius: radiusTopLeft + 'px',
          borderTopRightRadius: radiusTopRight + 'px',
          borderBottomLeftRadius: radiusBottomLeft + 'px',
          borderBottomRightRadius: radiusBottomRight + 'px'
        }"
      >
        <h5 class="text-title">
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum."
        </h5>
      </div>
      <hr />
      <div class="jumbotron">
        <h5 class="display-4">Copy your changes!</h5>
        <pre> 
          <code id="code-text" class="lead code-style">
      .class-name { 
        border-top-left-radius: {{ radiusTopLeft }}px;
        border-top-right-radius: {{ radiusTopRight }}px;
        border-bottom-right-radius: {{ radiusBottomRight }}px; 
        border-bottom-left-radius: {{ radiusBottomLeft }}px;
      }
        </code>
        </pre>

        <hr class="my-4" />
        <!-- <button class="btn btn-primary btn-lg" @click="copyToClipBoard">
          Copy Text
        </button> -->
        <button
          class="btn btn-primary btn-lg"
          type="text"
          @click="copyToClipBoard"
          v-clipboard:copy="textCode"
        >
          Copy Text
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      textCode: "",
      radiusTopLeft: 0,
      radiusTopRight: 0,
      radiusBottomRight: 0,
      radiusBottomLeft: 0
    };
  },
  methods: {
    copyToClipBoard() {
      let copyText = document.getElementById("code-text").innerText;
      this.textCode = copyText;
    }
  }
};
</script>

<style>
.container {
  min-height: 100%;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.text {
  margin-left: 1em;
}

.text-example-area {
  margin-top: 5em;
  border: 2px solid black;
}

.text-title {
  padding: 50px;
}

.code-style {
  color: #e83e8c;
}

.example-div {
  /* border-top-left-radius: ${pixelNumber}px */
}
</style>

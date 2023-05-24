<template>
  <div id="card">
    <model-viewer :src="modelSrc" poster="https://firebasestorage.googleapis.com/v0/b/vdesigners-5b906.appspot.com/o/images%2Flogo-new-white.png?alt=media&token=b6b30a6a-bf07-4216-af8a-eac2f459eb37" alt="v-designers logo" shadow-intensity="1" camera-controls auto-rotate ar></model-viewer>
    <section class="attribution">
      <span>
        <h1>Augmented Reality</h1>
        <span>By <a href="https://vdesigners-site.netlify.app/" target="_blank">V-DESIGNERs</a></span>
      </span>
      <!-- <a class="cc" href="https://creativecommons.org/licenses/by/2.0/" target="_blank">
        <img src="https://mirrors.creativecommons.org/presskit/icons/cc.svg" />
        <img src="https://mirrors.creativecommons.org/presskit/icons/by.svg" />
      </a> -->
    </section>
  </div>
</template>

<script>
//import '@google/model-viewer/dist/model-viewer.min.js';
export default {
  name: "ARModelViewer",
  data() {
    return {
      modelSrc: "",
      posterSrc: require("@/assets/load-icon.png") + "?v=" + Date.now(),
    };
  },
  mounted() {
    const urlParams = new URLSearchParams(window.location.search);
    console.log(urlParams);
   
    // Decode and handle the URL as you mentioned
    let decodedUrl = decodeURIComponent(urlParams.get("data"));
    console.log("simpledecoded",decodedUrl)
    decodedUrl = decodedUrl.replace("PLACEHOLDER", "%2F");

    this.modelSrc = decodedUrl;
    console.log("url in Augmented reality", this.modelSrc); // Output: "value1"
  },
};
</script>

<style scoped>
#card {
  margin: 3em auto;
  display: flex;
  flex-direction: column;
  max-width: 600px;
  border-radius: 6px;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.25);
  overflow: hidden;
}

model-viewer {
  width: 100%;
  height: 400px;
  background-color: #70bcd1;
  --poster-color: #ffffff00;
}

.attribution {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin: 1em;
}

.attribution h1 {
  margin: 0 0 0.25em;
}

.attribution img {
  opacity: 0.5;
  height: 2em;
}

.attribution .cc {
  flex-shrink: 0;
  text-decoration: none;
}
.ar-model-viewer {
  width: 100%;
  height: 400px;
  background-color: #70bcd1;
  --poster-color: #ffffff00;
}

</style>

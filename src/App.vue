<template>
  <div class="mainBox bg-dark py-5">
    <ul
      class="
        nav nav-pills nav-fill
        gap-2
        p-1
        small
        bg-secondary
        rounded-5
        shadow-sm
        container
      "
      id="pills-tab"
      role="tablist"
    >
      <li class="nav-item" role="presentation">
        <button
          class="nav-link text-light active rounded-5"
          id="pills-home-tab"
          data-bs-toggle="pill"
          data-bs-target="#pills-home"
          type="button"
          role="tab"
          aria-controls="pills-home"
          aria-selected="true"
        >
          Home
        </button>
      </li>
      <li class="nav-item" role="presentation">
        <button
          class="nav-link text-light rounded-5"
          id="pills-profile-tab"
          data-bs-toggle="pill"
          data-bs-target="#pills-profile"
          type="button"
          role="tab"
          aria-controls="pills-profile"
          aria-selected="false"
        >
          IMAGE GENERATOR
        </button>
      </li>
      <li class="nav-item" role="presentation">
        <button
          class="nav-link text-light rounded-5"
          id="pills-contact-tab"
          data-bs-toggle="pill"
          data-bs-target="#pills-contact"
          type="button"
          role="tab"
          aria-controls="pills-contact"
          aria-selected="false"
        >
          CODE GENERATOR
        </button>
      </li>
    </ul>
    <div
      class="tab-content bg-dark"
      id="pills-tabContent"
      style="min-height: 100vh"
    >
      <div
        class="tab-pane fade show active"
        id="pills-home"
        role="tabpanel"
        aria-labelledby="pills-home-tab"
        tabindex="0"
      >
        <div
          class="container d-flex gap-1 flex-wrap mt-4 justify-content-center"
        >
          <div class="col-sm-12">
            <div class="card bd-placeholder-img card-img">
              <img class="img-fluid" src="./assets/codeSnap.png" alt="" />
            </div>
          </div>
          <div class="col-sm-12">
            <div class="card bd-placeholder-img card-img">
              <img class="img-fluid" src="./assets/codeSnap1.png" alt="" />
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap2.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap3.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap4.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap5.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap6.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap7.png" alt="" />
              </div>
            </div>
            <div class="col-sm-12 col-lg-12 mt-3">
              <div class="card bd-placeholder-img card-img">
                <img class="img-fluid" src="./assets/codeSnap8.png" alt="" />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="tab-pane fade"
        id="pills-profile"
        role="tabpanel"
        aria-labelledby="pills-profile-tab"
        tabindex="0"
      >
        <form
          @submit.prevent="imageGeneratorHandler(inputText)"
          class="container mt-3"
        >
          <div class="box d-flex justify-content-end">
            <svg
              @click="speechRecogniser('mic1')"
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              id="mic1"
              fill="red"
              class="bi bi-mic-fill mt-3"
              viewBox="0 0 16 16"
              style="position: absolute"
            >
              <path d="M5 3a3 3 0 0 1 6 0v5a3 3 0 0 1-6 0V3z" />
              <path
                d="M3.5 6.5A.5.5 0 0 1 4 7v1a4 4 0 0 0 8 0V7a.5.5 0 0 1 1 0v1a5 5 0 0 1-4.5 4.975V15h3a.5.5 0 0 1 0 1h-7a.5.5 0 0 1 0-1h3v-2.025A5 5 0 0 1 3 8V7a.5.5 0 0 1 .5-.5z"
              />
            </svg>
            <input
              type="text"
              name=""
              id="text-input"
              v-model="inputText"
              class="form-control py-3"
              placeholder="Enter Something To generate AI based Images"
            />
          </div>
          <button type="submit" class="btn btn-secondary w-100">
            Generate Image
          </button>
        </form>
        <div class="container" v-if="imgUrl">
          <img
            :src="imgUrl"
            alt="no image Found"
            class="img-fluid container mt-5"
          />
        </div>
        <div v-if="flag1" class="container text-secondary" role="status">
          <p class="placeholder-glow" v-for="item in 12" :key="item">
            <span class="placeholder col-12"></span>
          </p>
        </div>
      </div>
      <div
        class="tab-pane fade"
        id="pills-contact"
        role="tabpanel"
        aria-labelledby="pills-contact-tab"
        tabindex="0"
      >
        <form
          @submit.prevent="textGeneratorHandler(inputText2)"
          class="container"
        >
          <div class="box d-flex justify-content-end">
            <svg
              @click="speechRecogniser('mic2')"
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              id="mic2"
              fill="red"
              class="bi bi-mic-fill mt-5"
              viewBox="0 0 16 16"
              style="position: absolute"
            >
              <path d="M5 3a3 3 0 0 1 6 0v5a3 3 0 0 1-6 0V3z" />
              <path
                d="M3.5 6.5A.5.5 0 0 1 4 7v1a4 4 0 0 0 8 0V7a.5.5 0 0 1 1 0v1a5 5 0 0 1-4.5 4.975V15h3a.5.5 0 0 1 0 1h-7a.5.5 0 0 1 0-1h3v-2.025A5 5 0 0 1 3 8V7a.5.5 0 0 1 .5-.5z"
              />
            </svg>
            <input
              type="text"
              name=""
              id="text-input"
              v-model="inputText2"
              autocomplete=""
              class="form-control mt-4 py-3"
              placeholder="Enter Something To generate AI based code or text"
            />
          </div>
          <button type="submit" class="btn btn-secondary w-100">
            Generate Text
          </button>
        </form>
        <ssh-pre
          reactive
          copy-button
          language="js"
          dark
          class="container d-flex justify-content-around border-secondary"
          v-for="item in codeArray"
          :key="item.index"
        >
          <template #copy-button>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="25"
              height="25"
              fill="white"
              class="bi bi-clipboard"
              viewBox="0 0 16 16"
            >
              <path
                d="M4 1.5H3a2 2 0 0 0-2 2V14a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3.5a2 2 0 0 0-2-2h-1v1h1a1 1 0 0 1 1 1V14a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V3.5a1 1 0 0 1 1-1h1v-1z"
              />
              <path
                d="M9.5 1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-3a.5.5 0 0 1-.5-.5v-1a.5.5 0 0 1 .5-.5h3zm-3-1A1.5 1.5 0 0 0 5 1.5v1A1.5 1.5 0 0 0 6.5 4h3A1.5 1.5 0 0 0 11 2.5v-1A1.5 1.5 0 0 0 9.5 0h-3z"
              />
            </svg>
          </template>
          {{ item.text }}
        </ssh-pre>

        <p
          v-if="generatedText2"
          class="
            card card-body
            container
            d-flex
            justify-content-center
            mt-3
            rounded-3
            text-center
            bg-dark
            border-secondary
            text-light
          "
        >
          {{ generatedText2 }}
        </p>
        <div v-if="flag2" class="container text-secondary" role="status">
          <p class="placeholder-glow" v-for="item in 12" :key="item">
            <span class="placeholder col-12"></span>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { Configuration, OpenAIApi } from "openai";
import SshPre from "simple-syntax-highlighter";
import "simple-syntax-highlighter/dist/sshpre.css";

export default {
  name: "App",
  data() {
    return {
      inputText: "",
      copiedText: "",
      imgUrl: "",
      openai: null,
      flag1: false,
      flag2: false,
      inputText2: "",
      generatedText1: "",
      generatedText2: "",
      codeArray: [],
    };
  },
  components: { SshPre },
  created() {
    const configuration = new Configuration({
      apiKey: import.meta.env.VITE_API_KEY,
    });
    this.openai = new OpenAIApi(configuration);
  },

  methods: {
    speechRecogniser: async function (val) {
      const btn = document.querySelector(`#${val}`);

      window.SpeechRecognition =
        window.webkitSpeechRecognition || window.SpeechRecognition;
      const recognition = new SpeechRecognition();

      recognition.onstart = () => {
        btn.classList.add("listening-animation");
        // btn.innerText = "Listening...";
      };

      recognition.onresult = (event) => {
        const current = event.resultIndex;
        if (val === "mic1") {
          this.inputText = event.results[current][0].transcript;
        } else {
          this.inputText2 = event.results[current][0].transcript;
        }
        btn.classList.remove("listening-animation");

        btn.innerHTML =
          '<svg xmlns="http://www.w3.org/2000/svg"  width="16" height="16"  fill="red"  class="bi bi-mic-fill"  viewBox="0 0 16 16"  > <path d="M5 3a3 3 0 0 1 6 0v5a3 3 0 0 1-6 0V3z" /> <path   d="M3.5 6.5A.5.5 0 0 1 4 7v1a4 4 0 0 0 8 0V7a.5.5 0 0 1 1 0v1a5 5 0 0 1-4.5 4.975V15h3a.5.5 0 0 1 0 1h-7a.5.5 0 0 1 0-1h3v-2.025A5 5 0 0 1 3 8V7a.5.5 0 0 1 .5-.5z"  /> </svg>';
      };

      recognition.start();
    },
    imageGeneratorHandler: async function (val) {
      this.flag1 = true;
      if (val) {
        const response = await this.openai.createImage({
          prompt: this.inputText,
          n: 1,
          size: "1024x1024",
        });
        console.log(response.data.data[0].url);
        this.imgUrl = response.data.data[0].url;
        this.flag1 = false;
      }
    },
    checkForCodeRequest(inpValue) {
      const keywords = [
        "generate code",
        "write code",
        "write a code",
        "code for",
        "how to",
        "route",
        "router",
        "java",
        "create code",
        "code to",
        "make code",
        "program for",
        "develop code",
        "script for",
        "build code",
        "produce code",
        "coding for",
        "create program",
        "scripting for",
        "code generation",
        "generate programming",
        "write a program",
        "coding help",
        "programming assistance",
      ];

      const pattern = new RegExp(`\\b(${keywords.join("|")})\\b`, "i");
      return pattern.test(inpValue);
    },
    textGeneratorHandler: async function (val) {
      const bool = this.checkForCodeRequest(val);

      this.flag2 = true;
      if (bool) {
        this.codeArray.length = 0;
        this.generatedText2 = "";
        const completion = await this.openai.createCompletion({
          model: "text-davinci-003",
          prompt: this.inputText2,
          max_tokens: 1024,
          n: 10,
          temperature: 1.0,
        });
        this.codeArray = completion.data.choices;
        this.generatedText1 = completion.data.choices[0].text;
        this.flag2 = false;
      } else {
        this.codeArray.length = 0;
        this.generatedText2 = "";
        const completion = await this.openai.createCompletion({
          model: "text-davinci-003",
          prompt: this.inputText2,
          max_tokens: 1024,
          n: 5,
          temperature: 1.0,
        });

        this.generatedText2 = completion.data.choices[0].text;
        this.flag2 = false;
      }
    },
  },
};
</script>
<style scoped>
code {
  font-family: "Source Code Pro", monospace;
  line-height: 18px;
}
.listening-animation {
  animation: listening 1s ease-in-out infinite;
}

@keyframes listening {
  0% {
    transform: scale(1);
  }
  25% {
    transform: scale(1.5);
  }
  75% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
/* .active {
  background-color: white !important;
  color: black !important;
} */
</style>

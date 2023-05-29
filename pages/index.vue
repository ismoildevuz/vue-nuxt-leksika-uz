<template>
  <section class="home-page py-10">
    <Container>
      <div class="wrapper max-w-[900px] mx-auto">
        <SearchBoxWord @search="sendReq" />

        <div v-if="words.length">
          <WordCard v-for="(el, ind) in words" :key="ind" :el="el" />
        </div>

        <div
          v-else-if="errorMessage"
          class="min-h-[500px] flex items-center justify-center"
        >
          <div>
            <img src="../assets/images/not-found.png" alt="" />
          </div>
          <div class="w-[60%]">
            <h2
              class="text-center text-[24px] leading-[36px] font-semibold mb-5"
            >
              Oops, no such word found!
            </h2>
            <div class="relative flex items-center justify-center">
              <div class="absolute -z-10">
                <img src="../assets/icons/text-bg-ellipse.svg" alt="" />
              </div>
              <div>
                <p
                  class="not-found-text text-center text-[18px] leading-[27px]"
                >
                  If you believe there is such a word in the language of
                  Shakespeare, please take a few seconds to report it via
                  <a href="#">Telegram</a> or <a href="#">Gmail</a> and we will
                  add it asap!
                </p>
              </div>
            </div>
          </div>
        </div>

        <div v-else class="min-h-[500px] flex items-center justify-center">
          <div class="relative flex items-center justify-center w-[70%]">
            <div class="absolute">
              <img src="../assets/icons/text-bg-ellipse.svg" alt="" />
            </div>
            <div>
              <p class="text-center text-[24px] leading-[36px]">
                Search any words, and we found this word defination, translation
                and etc.
              </p>
            </div>
          </div>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
const words = ref([]);
const errorMessage = ref("");

const sendReq = async (word) => {
  const { data } = await useFetch(
    `https://api.dictionaryapi.dev/api/v2/entries/en/${word}`
  );
  if (data.value) {
    words.value = data.value;
  } else {
    words.value = [];
    errorMessage.value = "error";
  }
  console.log(words.value);
};

var arr = [
  {
    word: "hello",
    phonetics: [
      {
        audio:
          "https://api.dictionaryapi.dev/media/pronunciations/en/hello-au.mp3",
        sourceUrl: "https://commons.wikimedia.org/w/index.php?curid=75797336",
        license: {
          name: "BY-SA 4.0",
          url: "https://creativecommons.org/licenses/by-sa/4.0",
        },
      },
      {
        text: "/həˈləʊ/",
        audio:
          "https://api.dictionaryapi.dev/media/pronunciations/en/hello-uk.mp3",
        sourceUrl: "https://commons.wikimedia.org/w/index.php?curid=9021983",
        license: {
          name: "BY 3.0 US",
          url: "https://creativecommons.org/licenses/by/3.0/us",
        },
      },
      {
        text: "/həˈloʊ/",
        audio: "",
      },
    ],
    meanings: [
      {
        partOfSpeech: "noun",
        definitions: [
          {
            definition: '"Hello!" or an equivalent greeting.',
            synonyms: [],
            antonyms: [],
          },
        ],
        synonyms: ["greeting"],
        antonyms: [],
      },
      {
        partOfSpeech: "verb",
        definitions: [
          {
            definition: 'To greet with "hello".',
            synonyms: [],
            antonyms: [],
          },
        ],
        synonyms: [],
        antonyms: [],
      },
      {
        partOfSpeech: "interjection",
        definitions: [
          {
            definition:
              "A greeting (salutation) said when meeting someone or acknowledging someone’s arrival or presence.",
            synonyms: [],
            antonyms: [],
            example: "Hello, everyone.",
          },
          {
            definition: "A greeting used when answering the telephone.",
            synonyms: [],
            antonyms: [],
            example: "Hello? How may I help you?",
          },
          {
            definition:
              "A call for response if it is not clear if anyone is present or listening, or if a telephone conversation may have been disconnected.",
            synonyms: [],
            antonyms: [],
            example: "Hello? Is anyone there?",
          },
          {
            definition:
              "Used sarcastically to imply that the person addressed or referred to has done something the speaker or writer considers to be foolish.",
            synonyms: [],
            antonyms: [],
            example:
              "You just tried to start your car with your cell phone. Hello?",
          },
          {
            definition: "An expression of puzzlement or discovery.",
            synonyms: [],
            antonyms: [],
            example: "Hello! What’s going on here?",
          },
        ],
        synonyms: [],
        antonyms: ["bye", "goodbye"],
      },
    ],
    license: {
      name: "CC BY-SA 3.0",
      url: "https://creativecommons.org/licenses/by-sa/3.0",
    },
    sourceUrls: ["https://en.wiktionary.org/wiki/hello"],
  },
];
</script>

<style lang="scss" scoped>
.not-found-text a {
  font-weight: 600;
  color: $main;
}

.not-found-text a:hover {
  text-decoration: underline;
}
</style>

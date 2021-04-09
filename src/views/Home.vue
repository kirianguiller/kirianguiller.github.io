<template>
  <div id="content">
    <div class="bg-light" id="header">
      <h1 class="site-header dark">Hi, I'm Kirian Guiller .</h1>
      <h2 class="site-subheader main">
        An NLP researcher & full-stack developper
      </h2>
    </div>
    <div class="bg-light divider">
      <hr class="rounded" />
    </div>
    <div id="experience" class="bg-light section">
      <h2 class="dark">Experience</h2>
      <ExperienceCard src="/img/sorbonne_nouvelle.svg">
        <template v-slot:title>Sorbonne Nouvelle University</template>
        <template v-slot:detail
          >Natural Language Processing Researcher</template
        >
        <template v-slot:place>Paris</template>
        <template v-slot:date>2019 - 2020</template>
        <template v-slot:description
          >My interests in languages made me want to learn more about
          linguistics and to specialized my data science and programming skills
          to Natural Language Processing. I naturally decided to attend to a
          Master of Science in NLP in Sorbonne Nouvelle University in
          partnership with INALCO and Paris Nanterre University.</template
        >
      </ExperienceCard>
      <ExperienceCard>
        <template v-slot:title>Le Mas de Julie - Restaurant</template>
        <template v-slot:detail>Associate - Online Presence Manager</template>
        <template v-slot:place>Montpellier</template>
        <template v-slot:date>2019 - Now</template>
        <template v-slot:description
          >In 2019, we decided, my parents and me, to open a restaurant in our
          home town near Montpellier. My charge of responsabilities is to deal
          with the <strong>online presence</strong>, such as designing the
          website, creating and managing Tripadvisor and Google My Business
          account. <br />
          Because I always liked <strong>photography</strong>, I'm also the one
          in charge for taking pictures and visual advertisement.<br />
          Opening and running a restaurant is a really good experience that is
          teaching me a lot about how to run a local business, talk with
          custumers, understand the needs and deal with pressure.</template
        >
      </ExperienceCard>
      <ExperienceCard>
        <template v-slot:title>ReadItEasy</template>
        <template v-slot:detail>Founder</template>
        <template v-slot:place>Paris</template>
        <template v-slot:date>2020 - Now</template>
        <template v-slot:description
          >I am developping an app for helping a language learner to read in his
          targets languages. I'm using Vuejs framework for the frontend and
          Django framework (python) for the backend. <br />
          This project is really complete and I can develop my frontend skills
          (html/css/javascript) as well as backend and database skills <br />
          Also, I implemented some NLP algorithms such as tokenizer (for
          detecting words in languages that don't use space indentation like
          chinese or japanese), word embeddings similarity, dependency parsing
          and others.</template
        >
      </ExperienceCard>
      <ExperienceCard src="/img/mpdata.png">
        <template v-slot:title>MPData</template>
        <template v-slot:detail>Data Scientist Junior</template>
        <template v-slot:place>Paris</template>
        <template v-slot:date>2017 - 2019</template>
        <template v-slot:description
          >I worked for a consulting company with missions clients such the
          first french tire production company as well as the first french
          electricity company. <br />
          During these missions, i developped machine learning algorithms for
          improving performance production such as predictive maintenance models
          (knn clustering) or vision and times series neural networks (CNN/RNN).
          Neural and statistical models.</template
        >
      </ExperienceCard>
      <ExperienceCard src="/img/am.svg">
        <template v-slot:title>Arts et Métiers</template>
        <template v-slot:detail>M.S. of Engineering</template>
        <template v-slot:place>Paris / Aix-en-Provence</template>
        <template v-slot:date>2012 - 2017</template>
        <template v-slot:description
          >Arts et Métier is an industrial engineering school and top among the
          best in France. Entering this school is only possible after a national
          two weeks exam that need to be prepared two years in preparatory
          class. <br />
          During these 5 years, I learned advanced mathematics, physics,
          engineering and programming.</template
        >
      </ExperienceCard>
    </div>
    <div class="bg-light divider">
      <hr class="rounded" />
    </div>
    <div id="languages" class="bg-light section">
      <h2>Languages</h2>
      <div class="lc-container">
        <LanguageCard class="lc-item">
          <template v-slot:front-title>Chinese Mandarin</template>
          <template v-slot:front-text
            >It's the language I have the most fun using. The way of conveying
            informations feels very picturesque. The writing system, with words
            symbolized by characters, has a lot to do with that and I like
            allocating daily time writing chinese texts. It feels like painting.
            One of my favorites author is
            <a href="https://www.youtube.com/watch?v=9IFVyI98bBs">Jimmy Liao</a
            >, a taiwanese picture book writer. His books have a "The Little
            Prince" feeling, childish appearance with complex meanings and
            feelings.</template
          >
          <template v-slot:back-title>漢語</template>
          <template v-slot:back-text
            >我非常愛這個語言。我覺得是一種用圖畫表達方式類似。
            我喜歡跟我語言學老師們和同學們關於中文語法聊一聊。</template
          >
        </LanguageCard>
        <LanguageCard class="lc-item">
          <template v-slot:front-title>Japanese</template>
          <template v-slot:front-text
            >For my final year of engineering school, I've got the chance to go
            to MIE University in Japan as an exchange student. It's in the
            country side Japan that I could developed my adaptative skills. As
            well for the language than for the culture. I've really enjoy
            learning Japanese and it gave me good basics and habbits for my
            Chinese learning. In the future, I want to go back to Japan working
            for a while and improve my skills.</template
          >
          <template v-slot:back-title>日本語</template>
          <template v-slot:back-text
            >私の日本語のレベルはめっちゃ簡単です。でも、日本で一年間で住むこと私の中国語のレベルのおかげで私は読むがちょっとできる。</template
          >
        </LanguageCard>
        <LanguageCard class="lc-item">
          <template v-slot:front-title>English</template>
          <template v-slot:front-text>Add english description</template>
          <template v-slot:back-title>日本語</template>
          <template v-slot:back-text
            >私の日本語のレベルはめっちゃ簡単です。でも、日本で一年間で住むこと私の中国語のレベルのおかげで私は読むがちょっとできる。</template
          >
        </LanguageCard>
      </div>
    </div>
    <h1 id="it-skills">IT Skills</h1>
    <h1 id="other">Other</h1>
  </div>
</template>

<script>
import ExperienceCard from "@/components/ExperienceCardflex.vue";
import LanguageCard from "@/components/LanguageCard.vue";
// import FlipCard from "@/components/FlipCard2.vue";
export default {
  components: {
    ExperienceCard,
    LanguageCard
    // FlipCard
  }
};
</script>

<style scoped>
#content {
  position: relative;
  top: 60px;
}

.site-header {
  font-family: var(--font-headline);
  font-weight: 500;
  margin-bottom: 0px;
  margin-top: 0px;
}
.site-subheader {
  font-size: 1.6em;
}

#header {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.section {
  padding: 100px 5%;
}

div#experience {
  /* padding-top: 100px; */
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section h2 {
  margin-bottom: 30px;
}

hr.rounded {
  border-top: 5px solid var(--color-main);
  border-radius: 5px;
  width: 100px;
  margin: 0 auto;
}

.divider {
  margin: 0px;
}

#languages {
  padding-left: 30px;
  padding-right: 30px;
}

.lc-container {
  /* margin: auto; */
  width: 100%;
  text-align: center;
  /* display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  justify-content: center; */
}

.lc-item {
  /* display: inline-block;   */
  /* margin: 0 30px 30px 30px; */
  margin: 30px auto;
}

#test {
  background-color: var(--main-txt-color);
}
</style>

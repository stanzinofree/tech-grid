<template>
  <Layout>
    <PageHeader>
      <template v-slot:image>
        <g-image src="~/assets/images/marvin-meyer-SYTO3xs06fU-unsplash.jpg" />
      </template>
      <template v-slot:content>
        <p class="text-3xl md:text-4xl">
          Write->Debug->StackOverflow->Start Again! 
        </p>
        <p class="text-lg md:text-2xl">
          Fare errori è un ciclo infinito che ci insegna a farne sempre di peggio con l'aiuto di altri che ne sanno meno di noi!!!
        </p>
      </template>
    </PageHeader>
    <div class="container text-center mx-auto">
      <SectionLatestArticles />
    </div>


    <SectionThinkDifferent />
    
    <div class="container text-center mx-auto">
      <SectionLatestNews />
    </div>

    

    <SectionOpenSource />
  </Layout>
</template>

<script>
import PageHeader from '~/components/PageHeader'
import SectionLatestArticles from '~/components/sections/LatestArticles'
import SectionLatestNews from '~/components/sections/LatestNews'
import SectionThinkDifferent from '~/components/sections/ThinkDifferent'
import SectionOpenSource from '~/components/sections/OpenSource'

export default {
  metaInfo: {
    title: 'StanzinoTech'
  },
  components: {
    PageHeader,
    SectionLatestArticles,
    SectionLatestNews,
    SectionThinkDifferent,
    SectionOpenSource
  }
};
</script>

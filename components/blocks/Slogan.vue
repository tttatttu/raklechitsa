<template>
  <Container>
    <section class="slogan">
      <div class="slogan__container">
        <p class="slogan__content">
          {{ Content.title }}
          <span class="slogan__title">{{ Content.hashtag }}</span>
        </p>
      </div>
    </section>
  </Container>
</template>

<script>
import Container from '~/components/blocks/Container';
export default {
  props: {
    Content: Object,
  },
  components: {
    Container,
  },
};
</script>

<style scoped>
.slogan__container {
  text-align: center;
  color: #ffffff;
  background-color: #613a93;
  font-weight: normal;
  font-size: 30px;
  line-height: 46px;
  padding: 17px;
  text-transform: uppercase;
}

.slogan__content {
  max-width: 750px;
  margin: auto;
}

.slogan__title {
  font-weight: bold;
  font-size: 40px;
}
@media screen and (max-width: 1280px) {
  .slogan__content {
    font-size: 28px;
  }
  .slogan__title {
    font-size: 36px;
  }
}
@media screen and (max-width: 1024px) {
  .slogan__content {
    font-size: 24px;
    line-height: 40px;
  }
  .slogan__title {
    font-size: 32px;
  }
}
@media screen and (max-width: 768px) {
  .slogan__content {
    font-size: 22px;
    line-height: 36px;
    padding: 12px 0;
    max-width: 509px;
  }
  .slogan__title {
    font-size: 34px;
  }
}
@media screen and (max-width: 550px) {
  .slogan__content {
    font-size: 18px;
    line-height: 22px;
    padding: 12px 0;
    max-width: 509px;
  }
  .slogan__title {
    font-size: 23px;
  }
}
@media screen and (max-width: 425px) {
  .slogan__content {
    font-size: 16px;
    line-height: 20px;
    padding: 14px 0;
    max-width: 250px;
  }
}
</style>

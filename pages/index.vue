<template>
  <!-- 인트로 페이지 -->
  <main v-if="page === 0">
    <img src="" alt="원피스 캐릭터들" />
    <h1>나와 닮은 원피스 캐릭터 찾기!</h1>
    <h2>나와 닯은 원피스 캐릭터는 누구일까요?</h2>
    <Button
      tintColor="pink"
      text="테스트 시작"
      :clickEvent="startTest"
    ></Button>
  </main>
  <!-- 질문 페이지 -->
  <main v-else-if="page < 5">
    <Question />
  </main>
  <!-- 결과 페이지  -->
</template>

<script>
/**
 * 메인 페이지 안에 들어갈 것
 * 1. 인트로 페이지
 * 2. 조건부 렌더링을 통해 퀴즈 컴포넌트
 * 3. 페이지 이동 /result/_mbti
 */

export default {
  computed: {
    page() {
      return this.$store.state.page;
    },
  },
  methods: {
    startTest() {
      console.log("test");
      this.$store.commit("SET_PAGE", 1);
    },
  },
};
</script>

<style></style>

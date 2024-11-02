<template>
  <div class="home">
    <router-link to="/user">사용자목록</router-link>
    <button @click="getData">데이터 호출</button>
  </div>
</template>

<script>
import axios from 'axios';


export default {
  // CORS(Cross-Origin Resource Sharing)
  // 특정 교차 도메인 간 요청, 특히 ajax요청은 동일-출처 보안정책에 의해 기본적을 금지
  // Front-End 와 Back-End 사이 axios를 이용해 데이터를 불러 올때 local주소가 다르면 오류가 남
  // 허용방법
  // 1. 리소스 서비스 서버에서 특정 교차 도메인 등록  2. 요청하는 도메인 서버쪽 Proxy 설정으로 우회 접속
  name: 'HomeView',
  methods : {
    getData(){
    axios.get('api')
    .then((response)=>{
      console.log(response)
    })
    .catch((error)=>{
      console.log(error)
    })
    }
  }
}
</script>

<style scoped>
a {
  color: black;
  text-decoration: none;
  font-weight: bold;
  font-size: 1.5rem;
}
</style>

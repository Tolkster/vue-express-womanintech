<template>
  <div class="in-tech__banner index">
    <!-- <h3>{{content}}</h3> -->
    <img src="../images/error_egggo.png">
  </div>
</template>

<script>
import UserService from '../services/user.service';

export default {
  name: 'Home',
  data() {
    return {
      content: ''
    };
  },
  mounted() {
    UserService.getPublicContent().then(
      response => {
        this.content = response.data;
      },
      error => {
        this.content =
          (error.response && error.response.data) ||
          error.message ||
          error.toString();
      }
    );
  }
};
</script>

<style>
    .alerta-erro {
      color: red;
    }

    .in-tech__banner.index {
        margin: 2rem 8%;
    }

    .in-tech__banner.index img {
        width: 100%;
        border-radius: 20px;
    }
</style>
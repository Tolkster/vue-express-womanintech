<template>
    <div class="in-tech__banner-course">
        <div class="in-tech__course">
            <p class="in-tech__course__header--top">Html</p>
            <div class="container">
                <div class="row justify-content-between">
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-1>
                            <img src="../images/thumbnail.png">
                        </b-button>
                        <b-modal id="modal-1" title="Introdução">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Introdução</span>
                    </div>
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-2>
                            <img src="../images/thumbnail.png">
                        </b-button>
                        <b-modal id="modal-2" title="Primeiro componente">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Primeiro componente</span>
                    </div>
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-3>
                            <img src="../images/thumbnail.png">
                        </b-button>
                        <b-modal id="modal-3" title="Projeto">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Projeto</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="in-tech__course">
            <p class="b-top in-tech__course__header">CSS</p>
            <div class="container">
                <div class="row justify-content-between">
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-4>
                            <img src="../images/thumbnail2.png">
                        </b-button>
                        <b-modal id="modal-4" title="Introdução">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Introdução</span>
                    </div>
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-5>
                            <img src="../images/thumbnail2.png">
                        </b-button>
                        <b-modal id="modal-5" title="Primeiro componente">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Primeiro componente</span>
                    </div>
                    <div class="in-tech__img col-12 col-md-3">
                        <b-button v-b-modal.modal-6>
                            <img src="../images/thumbnail2.png">
                        </b-button>
                        <b-modal id="modal-6" title="Projeto">
                            <iframe width="560" height="315" src="https://www.youtube.com/embed/LVcE_tsH7zo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                        </b-modal>
                        <span>Projeto</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
import UserService from '../services/user.service';

export default {
  name: 'User',
  data() {
    return {
      content: ''
    };
  },
  mounted() {
    UserService.getUserBoard().then(
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

.btn {
    border-radius: 15px;
}

.btn-primary {
    background-color: #caf7e3;
    border: none;
    color: grey;
}

.btn-primary:hover {
    color: #fff !important;
    background-color: #5f939a !important;
    border-color: #5f939a !important;
}

.in-tech__banner-course {
    margin: 3rem;
    border: 3px solid black;
    border-radius: 20px;
}

.in-tech__course {
    margin-bottom: 15px;
}

.b-top {
    border-top: 2px solid black;
}

.in-tech__course p {
    width: 100%;
    padding: .5rem 0 .5rem 1rem;
    text-transform: uppercase;
    border-bottom: 1px solid  black;
    font-weight: bold;
}

.in-tech__img {
    text-align: center;
}

.in-tech__img img {
    width: 100%;
}

.in-tech__img span {
    display: block;
    margin-top: .5rem;
}

.in-tech__img popin-btn {
    cursor: pointer;
}

iframe {
    width: 100%;
}

.in-tech__course__header {
    background-color: #caf7e3;
}

.in-tech__course__header--top {
    background-color: #caf7e3;
    border-top-left-radius: 15px;
    border-top-right-radius: 15px;
}
</style>
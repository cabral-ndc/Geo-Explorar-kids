<template>
  <div>
    <header>
      <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <a class="navbar-brand" href="#">GEO KIDS - Site educacional de geografia voltada para crianças!</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item active">
              <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Sobre</a>
            </li>
          </ul>
          <form class="form-inline my-2 my-lg-0">
            <input class="form-control mr-sm-2" type="search" placeholder="Pesquisr" aria-label="Pesquisr">
            <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisr</button>
          </form>
        </div>
      </nav>
    </header>
    <main>
      <section class="jumbotron text-center">
        <h1 class="display-4">Explorador de Países</h1>
        <p class="lead">Descubra os países do mundo!</p>
        <p><a href="#" class="btn btn-primary btn-lg">Começar a explorar</a></p>
      </section>
      <section class="container">
        <div class="row">
          <div class="col-md-4">
            <h2>Países</h2>
            <ul class="listagem-paises">
              <li v-for="pais in paises" :key="pais.name" @click="selecionarPais(pais)">
                <img :src="pais.flag" :alt="pais.name" />
                {{ pais.name }}
              </li>
            </ul>
            <button class="botao-anterior" @click="navegarEntrePaginas('anterior')">Anterior</button>
            <button class="botao-proxima" @click="navegarEntrePaginas('proxima')">Próxima</button>
          </div>
          <div class="col-md-8">
            <h2>Detalhes do País</h2>
            <p v-if="paisSelecionado">
              <img :src="paisSelecionado.flag" :alt="paisSelecionado.name" />
              {{ paisSelecionado.name }}
            </p>
            <p v-if="paisSelecionado">
              Capital: {{ paisSelecionado.capital }}
            </p>
            <p v-if="paisSelecionado">
              População: {{ paisSelecionado.population }}
            </p>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      paises: [],
      paisSelecionado: null
    }
  },
  methods:

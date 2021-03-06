<template>
  <client-only>
    <nav class="navbar-container" uk-navbar>
      <div class="navbar-left">
        <ul class="navbar-nav">
          <li class="active">
            <nuxt-link tag="a" class="navbar-brand" to="/" exact
              >Local Team</nuxt-link
            >
          </li>
          <li>
            <nuxt-link tag="a" class="navbar-brand" to="/clubs" exact
              >Browse Clubs</nuxt-link
            >
          </li>
        </ul>
      </div>
    </nav>
  </client-only>
</template>

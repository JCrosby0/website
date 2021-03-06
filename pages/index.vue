<template>
  <div class="container">
    <div class="main-search-container">
      <h1 class="title">Find a Local Club</h1>
      <div class="main-search">
        <input
          type="text"
          placeholder="Search for a sport, suburb or post-code"
        />
        <button value="Search">🔍</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

body {
  background-image: linear-gradient(
      to right,
      rgb(167, 253, 196) 0%,
      rgb(130, 248, 130) 50%,
      rgb(167, 253, 196) 100%
    ),
    url('~/assets/background.jpg');
  background-blend-mode: color-dodge;
}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
.main-search {
  padding: 1rem;
  font-size: 1.5rem;
  border: 2px grey solid;
  border-radius: 1rem;
  width: clamp(40%, 766px, 95%);
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
}
.main-search input {
  flex: 1 1 auto;
  border: none;
  outline: none;
  background: none;
}
.main-search button {
  flex: 0 0 auto;
}
.main-search-container {
  padding: 4rem;
  border-radius: 2rem;
  border: 1px grey solid;
  background: rgba(200, 255, 200, 0.9);
  box-shadow: 0 0 2rem 2rem rgba(200, 255, 200, 0.3);
}
.main-search:focus {
  border: none;
  border-radius: 1rem;
  font-size: 1.5rem;
  border: 2px green solid;
  outline: none;
}
</style>

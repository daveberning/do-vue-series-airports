<template>
  <div class="wrapper">
    <h1>Dave Berning</h1>
    <p>I am from Cincinnati, OH. I have two dogs, Hank (5) and Dale (6).</p>
    <p>I like music and food.</p>
    <ul>
      <li>Nirvana</li>
      <li>Green Day</li>
      <li>Foo Fighters</li>
    </ul>
  </div>
</template>

<script>
import DevData from '@/data/airports.development.mock'
import StagingData from '@/data/airports.staging.mock'

export default {
  name: 'App',
  computed: {
      airports() {
        if (process.env.NODE_ENV === 'development') return DevData
        else return StagingData
      }
  },
  mounted() {
    console.log(process.env.NODE_ENV)
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 1rem;
  max-width: 960px;
  margin: 0 auto;
}

.airport {
  border: 3px solid;
  border-radius: .5rem;
  padding: 1rem;
}

.airport p:first-child {
  font-weight: bold;
  font-size: 2.5rem;
  margin: 1rem 0;
}

.airport p:last-child {
  font-style: italic;
  font-size: .8rem;
}
</style>

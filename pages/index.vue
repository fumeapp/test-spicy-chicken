<template>
  <div class="container">
    <div>
      <Logo />
      <h3 class="title">
        test from cli
      </h3>
      <pre>
        config: {{ $config }}
      </pre>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      env: {
        test: 'ting',
        home: process.env.HOME,
        BASE_URL: process.env.BASE_URL,
      }
    }
  },
  mounted () {
    console.log(process.env)
    console.log(this.env)
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
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
</style>

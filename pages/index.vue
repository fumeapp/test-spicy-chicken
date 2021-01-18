<template>
  <div class="container">
    <div>
      <Logo />
      <h3 class="title">
        test spicy chicken
      </h3>
      <h4> runtime config ($config) </h4>
      <pre v-text="$config" />
      <h4> sample data from SSR </h4>
      <pre v-text="employees.length" />
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      employees: [],
    }
  },
  async fetch () {
    this.employees = (await fetch('http://dummy.restapiexample.com/api/v1/employees')
      .then(res => res.json())).data
  },
}
</script>

<style>

pre {
  width: 800px;
  text-align: left;
  margin: auto;
  padding: 10px;
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

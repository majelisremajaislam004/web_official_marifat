<template>
  <main>
    <navbar/>
      <div>
        <hai/>
      </div>
    <end/>
  </main>
</template>


<script>
export default {
  data() {
    return {
      items: '',
      loading: true,
    }
  },
  mounted() {
    this.ambilData()
  },
  methods: {
    async ambilData() {
      const { data,error } = await this.$supabase
      .form('about')
      .select()
      if(data)
        this.items = data
        this.loading = false
      if(error) console.log(error)
    }
  }
}
</script>


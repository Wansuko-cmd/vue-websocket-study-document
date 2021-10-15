<template>
  <div>
    <div class="m-5 text-left card p-3 col-10 col-lg-7 border-dark">
      <div>
        Text: {{ text }}
      </div>
      <div>
        UserName: {{ userName }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    userName: String,
    text: String,
  }
}
</script>

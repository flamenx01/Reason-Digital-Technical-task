<template>
<div class="form-section container">
  <h2>{{pageSection.page_section_title}}</h2>
  <p class="large-text">{{pageSection.page_section_text}}</p>
  <form>
    <label class="">I am a</label>
    <select class="" name="" id="">
			<option value="person">person</option>
			<option value="robot">robot</option>
			<option value="robotPerson">robot pretending to be a person</option>
		</select>
    <input type="submit" class="btn btn--alt-2" value="Start now">
  </form>
</div>
</template>

<script setup>
const props = defineProps({
   pageSection : { 
      type: Object, default: () => {
        return {}
      }
   },
});
</script>

<style lang="scss" scoped>
  .form-section {
    background-color: $grey-color;
    h2 {
        color: $dark-text;
      }
    p {
      margin-top: 1.5rem;
      color: $dark-text;
    }
    form {
      display: flex;
      justify-content: flex-start;
      align-items: flex-start;
      padding: 2.25em;
      margin-top: 2.25rem;
      background-color: $light-text;
      flex-wrap: wrap;
      flex-direction: column;
      label, select{
        font-size: 2rem;
        line-height: 1.4;
        font-weight: 300;
        margin-bottom: 1.5rem;
        @media (max-width: 45rem) {
          font-size: 1.25em;
          line-height: 1.4;
        }
      }
      label: {
        margin: 0 0 0 0.6rem;
      }
      select {
        background: none;
        border: none;
        border-bottom: 3px solid $main-color;
        color: $main-color;
        option {
          font-size: 1rem;
          color: $dark-text;
        }
      }
    }
  }
</style>
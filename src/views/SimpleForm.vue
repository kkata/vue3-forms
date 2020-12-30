<template>
  <div>
    <h1>Create an event</h1>
    <form>
      <BaseSelect
        :options="categories"
        v-model="event.category"
        label="Select a category"
      />

      <h3>Name & describe your event</h3>

      <BaseInput v-model="event.title" label="Title" type="text" />

      <BaseInput v-model="event.description" label="Desctiption" type="text" />

      <h3>Where is your event?</h3>

      <BaseInput v-model="event.location" label="Location" type="text" />

      <h3>Are pets allowed?</h3>
      <div>
        <input type="radio" v-model="event.pets" :value="1" name="pets" />
        <label>Yes</label>
      </div>

      <div>
        <input type="radio" v-model="event.pets" :value="0" name="pets" />
        <label>No</label>
      </div>

      <h3>Extras</h3>
      <div>
        <BaseCheckBox v-model="event.extras.catering" label="Catering" />
      </div>

      <div>
        <BaseCheckBox v-model="event.extras.music" label="Live music" />
      </div>

      <!-- <pre>{{ JSON.stringify(event, null, 2) }}</pre> -->

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      categories: [
        "sustainability",
        "nature",
        "animal welfare",
        "housing",
        "education",
        "food",
        "community"
      ],
      event: {
        category: "",
        title: "",
        description: "",
        location: "",
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      }
    };
  }
};
</script>

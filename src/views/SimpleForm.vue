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
        <BaseRadioGroup
          v-model="event.pets"
          name="pets"
          :options="petOptions"
        />
      </div>

      <h3>Extras</h3>
      <div>
        <BaseCheckBox v-model="event.extras.catering" label="Catering" />
      </div>

      <div>
        <BaseCheckBox v-model="event.extras.music" label="Live music" />
      </div>

      <pre>{{ JSON.stringify(event, null, 2) }}</pre>

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
      },
      petOptions: [
        { label: "Yes", value: 1 },
        { label: "No", value: 0 }
      ]
    };
  }
};
</script>

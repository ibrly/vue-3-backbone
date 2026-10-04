<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <form @submit.prevent="createMeetup">
          <label for="title">title</label>
          <input v-model="title"
                 class="form-control"
                 id="title"
                 type="text">
          <label for="desc">desc</label>
          <input v-model="desc"
                 class="form-control"
                 id="desc"
                 type="text">
          <label for="imgurl">imgurl</label>
          <input v-model="imgurl"
                 class="form-control"
                 id="imgurl"
                 type="text">
          <label for="address">address</label>
          <input v-model="address"
                 class="form-control"
                 id="address"
                 type="text">
          <label for="id">id</label>
          <input v-model="id"
                 id="id"
                 type="text">
          <button type="submit">Create</button>
          <button type="button"
                  v-on:click="updateMeetup">Update
          </button>
          <button type="button"
                  v-on:click="deleteMeetup">Delete
          </button>
        </form>

      </div>
    </div>
    <div class="row">
      <div v-bind:key="meetu"
           v-for="(meetu,index) of meetup"
           class="col-md-4">
        <div class="card mt-3"
             v-on:click="selectItem(index)">
          <div class="card-header"><h2 class="card-title">{{ meetu.title }}</h2></div>
          <div class="card-body p-0"><img class="img-fluid"
                                          v-bind:src="meetu.image"
                                          alt=""></div>
          <div class="card-footer"><p>{{ meetu.description }}</p></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {mapGetters} from "vuex";


export default {
  name: "Meetups",

  data() {
    return {
      title: '',
      desc: '',
      imgurl: '',
      address: '',
      myModal: null,
      failed: false,
      success: false,
      id: null,
      toastList: [],
      selected: 0,
      selectedItem: null
    }
  },
  methods: {
    selectItem(selected) { this.selected = selected },
    createMeetup() {
      this.$store.dispatch('createMeetups',
          {
            title: this.title,
            description: this.desc,
            address: this.address,
            image: this.imgurl
          });

    },
    updateMeetup() {

      this.$store.dispatch('updateMeetups',
          {
            id: this.id,
            title: this.title,
            description: this.desc,
            address: this.address,
            image: this.imgurl
          });

    },
    deleteMeetup() {

      this.$store.dispatch('deleteMeetup',
          {
            id: this.id
          });

    },
    getData() {
      this.$store.dispatch('getMeetups');
    }
  },
  computed: {
    ...mapGetters(['meetup'])
  }
  , mounted() {
    this.getData()
  },
  watch: {
    selected() {
      this.selectedItem = this.meetup[this.selected]
      this.title = this.selectedItem.title
      this.desc = this.selectedItem.description
      this.imgurl = this.selectedItem.image
      this.address = this.selectedItem.address
      this.id = this.selectedItem.id
      console.log('ssdsds')
    }
  }
}
</script>

<style scoped>

</style>

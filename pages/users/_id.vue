<template>
  <div>
    <div v-if="user" class="container py-5">
      <div class="hero-container">
        <img
          :src="user.avatar"
          alt=""
          class="image"
        />
        <div class="info-box">
          <h1>{{ user.first_name }}</h1>
          <p class="snippet">{{ user.last_name }}</p>
          <RentModal />
        </div>
      </div>
      <div class="whats-included-container">
        <div class="included-container">
          <p>{{userInfo}}</p>
          <h6>Super Effective</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="included-container">
          <h6>Clean & Tidy</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="included-container">
          <h6>Cancel Anytime</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="included-container">
          <h6>Satisfaction Guaranteed</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
      </div>
      <Reviews />
    </div>
  </div>
</template>

<script>
import { mapActions, mapState, mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['userById']),
    ...mapState({
      user: state => state.simpleUser
    }),
    userInfo () {
      return this.$store.getters.userById(this.$route.params.id)
    }
  },
  mounted () {
    this.getSimpleUser(this.$route.params.id)
    !this.$store.usersInfo && this.getUsersInfo()
    
  },
  methods: {
    ...mapActions(['getSimpleUser', 'getUsersInfo']),
  },
}
</script>

<style scoped>
.hero-container {
  display: flex;
  justify-content: space-between;
}
.image {
  width: 200px;
}
.info-box {
  width: 39%;
  background-color: rgba(207, 201, 201, 0.322);
  padding: 1rem;
  border-radius: 0.5rem;
}
.whats-included-container {
  border-bottom: 0.1rem solid rgba(128, 128, 128, 0.151);
}
.description-container {
  border-bottom: 0.1rem solid rgba(128, 128, 128, 0.151);
  padding-bottom: 2rem;
  margin-bottom: 2rem;
}
.included-container {
  margin-top: 1.5rem;
}
h1 {
  font-size: 1.75rem;
}
h6 {
  font-size: 1.15rem;
  font-weight: 400;
}
p {
  color: grey;
}
.snippet {
  color: rgba(0, 0, 0, 0.774);
  margin-top: 1rem;
}
button {
  width: 100%;
  border: none;
  padding: 0.5rem;
  color: white;
  font-weight: 700;
  padding: 1rem 4rem;
  border-radius: 100rem;
  background-color: rgb(231, 81, 43);
  color: white;
  font-weight: 700;
  transition: 0.5s;
}
.description-container {
  margin-top: 3rem;
  color: grey;
}

</style>
<template>
  <AppHeader :wishlistCount="wishlistCount" />

  <main>
    <CourseCard
      v-for="course in courses"
      :key="course.id"
      :course="course"
      @save-course="saveCourse"
    />
  </main>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import CourseCard from './components/CourseCard.vue'

export default {
  components: { AppHeader, CourseCard },

  data() {
    return {
      courses: [
        { id: 1, title: 'Italian Pasta Mastery', chef: 'Chef Manie', level: 'Advanced', price: 1000, available: true, saved: false, image: 'https://imgs.search.brave.com/r_x73O1ilBrgal8QNJrRuA4j50iVBSuC7W1w5HuNjOo/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly9tZWRp/YS5pc3RvY2twaG90/by5jb20vaWQvMTQ3/MjUyNjcyMy9waG90/by9pdGFsaWFuLWN1/aXNpbmUtcGl6emEt/cGFzdGEtYW5kLXRv/YXN0cy5qcGc_Yj0x/JnM9NjEyeDYxMiZ3/PTAmaz0yMCZjPS00/VVRiZVRveEFzOGdW/RzlRZE56TTNMTlN5/QkNGTzZUMnBxdmFu/eWdqV009' },
        { id: 2, title: 'French Pastry Basics', chef: 'Chef Adriaanse', level: 'Advanced', price: 890, available: true, saved: false, image: 'https://images.unsplash.com/photo-1555507036-ab1f4038808a?w=400' },
        { id: 3, title: 'Sushi & Japanese Cuisine', chef: 'Chef Hiro', level: 'Intermediate', price: 750, available: false, saved: false, image: 'https://images.unsplash.com/photo-1579871494447-9811cf80d66c?w=400' },
        { id: 4, title: 'BBQ & Grilling Techniques', chef: 'Chef Sipho', level: 'Beginner', price: 500, available: true, saved: false, image: 'https://images.unsplash.com/photo-1529193591184-b1d58069ecdd?w=400' },
        { id: 5, title: 'Vegan Cooking Essentials', chef: 'Chef Aisha', level: 'Beginner', price: 420, available: true, saved: false, image: 'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?w=400' },
        { id: 6, title: 'Thai Street Food', chef: 'Chef Niran', level: 'Intermediate', price: 620, available: false, saved: false, image: 'https://images.unsplash.com/photo-1562565652-a0d8f0c59eb4?w=400' },
        { id: 7, title: 'Bread & Sourdough', chef: 'Chef Lena', level: 'Intermediate', price: 530, available: true, saved: false, image: 'https://images.unsplash.com/photo-1509440159596-0249088772ff?w=400' },
        { id: 8, title: 'Cape Malay Cuisine', chef: 'Chef Fatima', level: 'Advanced', price: 780, available: true, saved: false, image: 'https://images.unsplash.com/photo-1574484284002-952d92456975?w=400' },
      ]
    }
  },

  computed: {
    wishlistCount() {
      return this.courses.filter(c => c.saved).length
    }
  },

  methods: {
    saveCourse(id) {
      const course = this.courses.find(c => c.id === id)
      if (course) course.saved = true
    }
  }
}
</script>
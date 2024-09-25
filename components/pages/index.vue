<template>
  <div>
    <Header :name="cvData.name" :title="cvData.title" />
    <Profile :description="cvData.profile" />
    <Experience :experiences="cvData.experiences" />
    <Education :educationList="cvData.education" />
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Profile from '@/components/Profile.vue'
import Experience from '@/components/Experience.vue'
import Education from '@/components/Education.vue'

export default {
  components: {
    Header,
    Profile,
    Experience,
    Education
  },
  data() {
    return {
      cvData: {
        name: 'John Doe',
        title: 'Full-Stack Developer',
        profile: 'Experienced developer with a focus on front-end and back-end technologies...',
        experiences: [
          {
            title: 'Software Engineer',
            company: 'Tech Company',
            date: '2020 - Present',
            description: 'Working on various projects using modern web technologies...'
          },
          {
            title: 'Web Developer',
            company: 'Another Company',
            date: '2018 - 2020',
            description: 'Developed responsive websites and applications...'
          }
        ],
        education: [
          {
            degree: 'Bachelor of Science in Computer Science',
            institution: 'University XYZ',
            date: '2014 - 2018'
          }
        ]
      }
    }
  }
}
</script>

<style scoped>
div {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}
</style>

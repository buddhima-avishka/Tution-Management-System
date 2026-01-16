<template>
  <q-page class="bg-black text-white">
    <!-- Full Screen Header Wrapper -->
    <div class="column" style="min-height: 100vh">
      
      <!-- Navbar -->
      <div class="q-py-sm q-px-lg q-px-md-xl col-auto" style="max-width: 1300px; margin: 0 auto; width: 100%">
        <q-toolbar class="q-py-sm bg-transparent">
          <q-btn flat no-caps no-wrap class="q-ml-xs text-white">
            <q-icon name="school" size="28px" />
            <q-toolbar-title shrink class="text-weight-bold q-ml-sm">
              EduManager
            </q-toolbar-title>
          </q-btn>
          
          <q-space />

          <div class="gt-xs">
            <q-btn flat no-caps label="Features" color="white" />
            <q-btn flat no-caps label="About" color="white" />
          </div>
          
          <div class="q-pl-md">
            <q-btn unelevated color="white" text-color="black" label="Login" no-caps class="q-px-lg text-weight-bold" />
          </div>
        </q-toolbar>
      </div>

      <!-- Hero Section (Centered) -->
      <div class="col flex flex-center q-py-lg overflow-hidden">
        <div class="container q-px-lg q-px-md-xl w-full">
          <div class="row items-center q-col-gutter-xl reverse-wrap-md">
            <div class="col-12 col-md-6">
              <div class="hero-title text-weight-bolder text-white q-mb-md">
                Manage Your Tuition Class Like a Pro.
              </div>
              <p class="text-h6 text-grey-5 text-weight-regular q-mb-lg" style="line-height: 1.5; max-width: 500px;">
                The ultimate all-in-one platform to streamline attendance, payments, scheduling, and student performance. Experience the future of education management.
              </p>
              <div class="row q-gutter-md">
                <q-btn 
                  unelevated 
                  color="white" 
                  text-color="black" 
                  label="Get Started" 
                  size="lg" 
                  no-caps 
                  class="q-px-xl text-weight-bold"
                />
                <q-btn 
                  outline 
                  color="white" 
                  label="View Demo" 
                  size="lg" 
                  no-caps 
                  class="q-px-lg"
                />
              </div>
              
              <div class="row items-center q-mt-xl q-gutter-x-lg text-grey-5">
                <div class="row items-center">
                  <q-icon name="check_circle" color="white" size="20px" class="q-mr-sm" />
                  <span>Free 14-day trial</span>
                </div>
                <div class="row items-center">
                  <q-icon name="check_circle" color="white" size="20px" class="q-mr-sm" />
                  <span>No credit card required</span>
                </div>
              </div>
            </div>
            
            <div class="col-12 col-md-6 gt-sm">
              <q-img 
                src="~assets/hero-dark.png" 
                class="hero-image rounded-borders shadow-20 glowing-border"
                style="border-radius: 20px;"
              />
            </div>
          </div>
        </div>
      </div>

      <!-- Stats Section (Bottom) -->
      <div class="col-auto bg-grey-10 text-white q-py-lg border-top-bottom">
        <div class="container q-px-md">
          <div class="row justify-center q-col-gutter-xl q-gutter-y-lg text-center">
            <div class="col-6 col-md-3">
              <div class="text-h3 text-weight-bold">500+</div>
              <div class="text-subtitle1 text-grey-5 q-mt-xs">Institutes</div>
            </div>
            <div class="col-6 col-md-3">
              <div class="text-h3 text-weight-bold">50k+</div>
              <div class="text-subtitle1 text-grey-5 q-mt-xs">Students</div>
            </div>
            <div class="col-6 col-md-3">
              <div class="text-h3 text-weight-bold">99.9%</div>
              <div class="text-subtitle1 text-grey-5 q-mt-xs">Uptime</div>
            </div>
            <div class="col-6 col-md-3">
              <div class="text-h3 text-weight-bold">24/7</div>
              <div class="text-subtitle1 text-grey-5 q-mt-xs">Support</div>
            </div>
          </div>
        </div>
      </div>
    
    </div>

    <!-- Features Section -->
    <div class="q-py-xl section-features">
      <div class="container q-px-md q-py-lg">
        <div class="text-center q-mb-xl">
          <div class="text-overline text-grey-5 text-weight-bold">POWERFUL MODULES</div>
          <div class="text-h3 text-weight-bold text-white">Everything You Need</div>
          <div class="text-subtitle1 text-grey-5 q-mt-md" style="max-width: 600px; margin: 0 auto">
            We provide a comprehensive suite of tools designed to handle every aspect of your educational institution.
          </div>
        </div>

        <div class="row q-col-gutter-lg">
          <div class="col-12 col-sm-6 col-md-4" v-for="feature in features" :key="feature.title">
            <q-card flat bordered class="h-full feature-card bg-grey-10 border-grey-9">
              <q-card-section class="q-pa-lg text-center">
                <div class="q-mb-md flex flex-center">
                  <q-avatar color="grey-9" text-color="white" :icon="feature.icon" font-size="28px" size="60px" />
                </div>
                <div class="text-h6 text-weight-bold q-mb-sm text-white">{{ feature.title }}</div>
                <div class="text-grey-5">{{ feature.desc }}</div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </div>

    <!-- Mobile App Showcase -->
    <div class="q-py-xl">
      <div class="container q-px-md">
        <div class="row items-center q-col-gutter-xl">
          <div class="col-12 col-md-6">
            <q-img 
              src="~assets/feature-mobile.png" 
              class="rounded-borders shadow-10"
              style="border-radius: 20px;"
            />
          </div>
          <div class="col-12 col-md-6">
             <div class="text-overline text-grey-5 text-weight-bold">MOBILE FIRST</div>
             <div class="text-h3 text-weight-bold text-white q-mb-md">Stay Connected Anywhere</div>
             <p class="text-h6 text-grey-5 text-weight-regular q-mb-lg">
               Give your students and parents the power of information. Our dedicated mobile app allows for real-time notifications, result checking, and class scheduling on the go.
             </p>
             <q-list class="text-white">
               <q-item>
                 <q-item-section avatar>
                   <q-icon color="white" name="bolt" />
                 </q-item-section>
                 <q-item-section>Instant Notifications</q-item-section>
               </q-item>
               <q-item>
                 <q-item-section avatar>
                   <q-icon color="white" name="check_circle" />
                 </q-item-section>
                 <q-item-section>Easy Attendance Tracking</q-item-section>
               </q-item>
             </q-list>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Analytics Showcase -->
    <div class="q-py-xl">
      <div class="container q-px-md">
        <div class="row items-center q-col-gutter-xl reverse-wrap-md">
           <div class="col-12 col-md-6">
             <div class="text-overline text-grey-5 text-weight-bold">DEEP INSIGHTS</div>
             <div class="text-h3 text-weight-bold text-white q-mb-md">Data-Driven Decisions</div>
             <p class="text-h6 text-grey-5 text-weight-regular q-mb-lg">
               Visualize student performance and institute growth with advanced analytics. Make informed decisions based on real-time data.
             </p>
             <q-btn outline color="white" label="Explore Analytics" no-caps class="q-px-lg" />
           </div>
           <div class="col-12 col-md-6">
            <q-img 
              src="~assets/feature-analytics.png" 
              class="rounded-borders shadow-10"
              style="border-radius: 20px;"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- Call to Action -->
    <div class="q-py-xl q-my-xl">
      <div class="container q-px-md">
        <div class="bg-grey-10 text-white rounded-borders q-pa-xl text-center shadow-10 border-grey-9" style="border-radius: 24px; border: 1px solid #333;">
          <div class="text-h3 text-weight-bold q-mb-md">Ready to modernize your institute?</div>
          <div class="text-h6 text-grey-5 q-mb-xl" style="font-weight: 300;">
            Join hundreds of institutes delivering better education with EduManager.
          </div>
          <q-btn 
            unelevated 
            color="white" 
            text-color="black" 
            label="Start Your Free Trial" 
            size="lg" 
            no-caps 
            class="q-px-xl text-weight-bold"
          />
        </div>
      </div>
    </div>

    <!-- Footer -->
    <div class="bg-black text-grey-5 q-py-xl border-top">
      <div class="container q-px-md">
        <div class="row q-col-gutter-xl">
          <div class="col-12 col-lg-4">
            <div class="text-h6 text-white text-weight-bold q-mb-md flex items-center">
              <q-icon name="school" size="24px" class="q-mr-sm" />
              EduManager
            </div>
            <p>
              The most advanced tuition management platform built for modern educators. Streamline your operations today.
            </p>
          </div>
          <div class="col-6 col-lg-2">
            <div class="text-white text-weight-bold q-mb-md">Product</div>
            <div class="q-gutter-y-sm flex column">
              <a href="#" class="footer-link">Features</a>
              <a href="#" class="footer-link">Pricing</a>
              <a href="#" class="footer-link">Security</a>
            </div>
          </div>
          <div class="col-6 col-lg-2">
            <div class="text-white text-weight-bold q-mb-md">Company</div>
            <div class="q-gutter-y-sm flex column">
              <a href="#" class="footer-link">About Us</a>
              <a href="#" class="footer-link">Careers</a>
              <a href="#" class="footer-link">Contact</a>
            </div>
          </div>
          <div class="col-12 col-lg-4">
             <div class="text-white text-weight-bold q-mb-md">Subscribe</div>
             <p>Get the latest updates and resources.</p>
             <q-input dark dense outlined placeholder="Enter your email" v-model="email" class="q-mt-md">
                <template v-slot:append>
                  <q-btn flat dense color="white" icon="arrow_forward" />
                </template>
             </q-input>
          </div>
        </div>
        <q-separator dark class="q-my-lg" />
        <div class="row justify-between items-center">
          <div>© 2024 EduManager. All rights reserved.</div>
          <div class="q-gutter-x-md">
            <q-icon name="facebook" size="20px" class="cursor-pointer hover-white" />
            <q-icon name="link" size="20px" class="cursor-pointer hover-white" /> 
            <q-icon name="rss_feed" size="20px" class="cursor-pointer hover-white" />
          </div>
        </div>
      </div>
    </div>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const email = ref('')

const features = [
  {
    title: 'Student Management',
    desc: 'Keep track of student profiles, attendance records, and enrollment history in one secure place.',
    icon: 'people'
  },
  {
    title: 'Smart Scheduling',
    desc: 'Effortlessly manage class timetables, teacher allocations, and room bookings without conflicts.',
    icon: 'calendar_month'
  },
  {
    title: 'Automated Payments',
    desc: 'Handle tuition fees, generate invoices, and track outstanding payments with automated reminders.',
    icon: 'payments'
  },
  {
    title: 'LMS Integration',
    desc: 'Share study materials, assignments, and conducting online exams through our built-in Learning Management System.',
    icon: 'school'
  },
  {
    title: 'Performance Analytics',
    desc: 'Visual reports and dashboards to track student progress and institute financial health.',
    icon: 'analytics'
  },
  {
    title: 'Mobile App',
    desc: 'Dedicated mobile apps for students, parents, and teachers to stay connected on the go.',
    icon: 'smartphone'
  }
]
</script>

<style scoped>
.container {
  max-width: 1300px;
  margin: 0 auto;
}


.feature-card {
  transition: all 0.3s ease;
  height: 100%;
}

.feature-card:hover {
  transform: translateY(-5px);
  border-color: #ffffff;
  box-shadow: 0 10px 30px rgba(255,255,255,0.05);
}

.footer-link {
  color: #9e9e9e;
  text-decoration: none;
  transition: color 0.2s;
}

.footer-link:hover {
  color: white;
}

.border-grey-9 {
  border-color: #333;
}

.hero-title {
  font-size: 2.5rem;
  line-height: 1.1;
}

@media (min-width: 1024px) {
  .hero-title {
    font-size: 3.75rem;
  }
}

.border-top-bottom {
  border-top: 1px solid #222;
  border-bottom: 1px solid #222;
}

.border-top {
  border-top: 1px solid #222;
}

.glowing-border {
  box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
}

.hover-white:hover {
    color: white;
}

@media (max-width: 1023px) {
  .reverse-wrap-md {
    flex-direction: column-reverse;
  }
}
</style>

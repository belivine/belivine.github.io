<template>
  <div style="background-color: white">
    <md-toolbar class="md-accent" md-elevation="1">
      <h3 class="md-title">Belivine</h3>
      <md-button>Beranda</md-button>
      <md-button href=#feature>Fitur</md-button>
      <md-button href="https://wa.me/+6282210357112" target="blank_">Kontak</md-button>
    </md-toolbar>
    <div id="banner">
      <div class="container" style="display: flex">
        <div class="banner-left">
          <p>Selamat datang di Belivine</p>
          <h1>Kami Adalah Solusi</h1>
          <h1>Untuk Sistem Managemen Karyawan</h1>
        </div>
        <div class="banner-right">
          <img src="~/assets/images/banner-item.png" alt="" />
        </div>  
      </div>      
    </div>
    <div class="container">
      <div id="about" class="section">
        <h1>Apa itu Belivine?</h1>
        <p>
          Belivine merupakan Human Resource Management System yang akan membantu
          mempermudah pembisnis atau perusahaan dalam mengoleola data karyawan
        </p>
      </div>

      <div id="feature" class="section">
        <div class="md-layout md-gutter" v-for="(feature, idx) in features" :key="idx">
          <div class="md-layout-item md-medium-size-100 md-small-size-100 md-xsmall-size-100 right" v-if="idx % 2 == 0" style="align-items: center">
            <div v-for="(val, i) in feature.featureList" :key="i" >
              <div class="single-item md-layout-item md-medium-size-30 md-small-size-30 md-xsmall-size-30" v-for="(list, index) in val" :key="index">
                <md-icon class="item-icon" style="display: flex !important; justify-content: center; color: white">{{list.icon}}</md-icon>
                <p style="text-align: center; font-size: 0.625rem">{{ list.label }}</p>
              </div>
            </div>
          </div>
          <div v-if="idx % 2 == 0" class="md-layout-item md-medium-size-30 md-small-size-30 md-xsmall-size-100">
            <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
          </div>

          <div v-if="idx % 2 !== 0" class="md-layout-item right">
            <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
          </div>
          <div class="md-layout-item md-medium-size-100 md-small-size-100 md-xsmall-size-100" v-if="idx % 2 !== 0" style="align-items: center; display: flex">
            <div v-for="(val, i) in feature.featureList" :key="i" >
              <div class="single-item md-layout-item md-medium-size-30 md-small-size-30 md-xsmall-size-30" v-for="(list, index) in val" :key="index">
                <md-icon class="item-icon" style="display: flex !important; justify-content: center; color: white">{{list.icon}}</md-icon>
                <p style="text-align: center; font-size: 0.625rem">{{ list.label }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- <div id="carousel" class="section">
        <vueper-slides
          class="no-shadow"
          :visible-slides="3"
          :slide-ratio="1 / 4"
          :dragging-distance="70">
          <vueper-slide v-for="i in slides" :key="i" :image="i.image" />
        </vueper-slides>
      </div> -->
      
      <div id="contact" class="section">
        <md-button href="https://wa.me/+6282210357112" target="_blank" class="md-primary">
          <md-icon>whatsapp</md-icon>
          082210357112
        </md-button>
      </div>
    </div>
    <div id="footer">
        <div class="footer-content">
          <md-icon>mail</md-icon>
          <p>belivineofficial</p>
        </div>
        <div class="footer-content">
          <md-icon>mail</md-icon>
          <p>belivine</p>
        </div>
        <div class="footer-content">
          <md-icon>mail</md-icon>
          <p>belivine.team</p>
        </div>
        <div class="footer-content">
          <md-icon>location_on</md-icon>
          <p>Yogyakarta</p>
        </div>
      </div>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

export default {
  name: "IndexPage",
  components: {
    VueperSlides,
    VueperSlide
  },
  data() {
    return {
      screenWidth: 0,
      slides: [
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/hr.jpg')
        },
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/login.jpg')
        },
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/hr.jpg')
        },
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/hr.jpg')
        },
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/hr.jpg')
        },
        {
          title: 'Slide #1',
          content: 'Slide 1 content.',
          image: require('@/assets/images/hr.jpg')
        },
      ],
      features: [
        {
          name: "HR",
          image: "feature-hr.png",
          featureList: [
            [
              {
              icon: "event",
              label: "Timesheet",
              },
              {
                icon: "sticky_note_2",
                label: "Perijinan",
              },
            ],
            [
              {
                icon: "assignment",
                label: "Data Karyawan",
              },
              {
                icon: "edit_document",
                label: "Data Kontrak",
              }
            ],
            [
              {
                icon: "calendar_month",
                label: "Kalender",
              },
              {
                icon: "backup_table",
                label: "Dokumen Karyawan",
              },
            ]
          ],
        },
        {
          name: "Penggajian",
          image: "feature-payroll.png",
          featureList: [
            [
              {
                icon: "monetization_on",
                label: "Data Gaji",
              },
              {
                icon: "post_min",
                label: "Potongan Gaji",
              },
            ],
            [
              {
                icon: "post_add",
                label: "Bonus",
              },
              {
                icon: "home",
                label: "THR",
              },
            ],
            [
              {
                icon: "home",
                label: "Keuangan",
              },
            ]
          ],
        },
        {
          name: "Laporan",
          image: "feature-report.png",
          featureList: [
            [
              {
              icon: "home",
              label: "Penggajian",
              },
              {
                icon: "",
                label: "Keuangan",
              },
            ],
            [
              {
                icon: "home",
                label: "Kehadiran",
              },
              {
                icon: "home",
                label: "Kontrak",
              }
            ]
          ],
        },
      ],
    };
  },
  methods: {
    handleResize() {
      console.log('resize')
      this.screenWidth = screen.width;
      console.log(this.screenWidth)
    }
  },
  beforeMount() {
    window.addEventListener('resize', this.handleResize);
  },
  beforeDestroy() {
    window.addEventListener('resize', this.handleResize);
  },
  // created() {
  //   console.log('created')
  //   this.handleResize()
  // },
  destroyed() {
    // window.removeEventListener('resize', this.handleResize);
  }
};
</script>

<style>
.md-accent .md-title {
  flex: 1;
}

.md-toolbar.md-theme-default.md-accent {
  background-color: #1165ad;
  box-shadow: none;
}

.md-toolbar {
  padding: 0px 17.75rem;
}

#banner {
  height: 31.25rem;
  width: 100%;
  /* height: 51.98vh; */
  background-color: #1165ad;
  padding-top: 4.688rem;
  color: white;
  gap: 3.125rem;
}

#banner .banner-left h1 {
  font-size: 2.08vw;
}

.banner-right {
  /* margin-left: 3.125rem; */
  width: 30%;
}

#banner .banner-right img {
  width: 100%;
}

#banner .banner-left {
  width: 70%;
}

.section {
  padding-top: 50px;
  padding-bottom: 50px;
}

.container {
  margin-left: 18.75rem;
  margin-right: 18.75rem;
}

#about {
  text-align: center;
}

.container .md-layout {
  margin: 3.125rem 0;
}

.container .md-layout-item.right {
  display: flex;
  justify-content: flex-end;
}

.container .md-layout-item .single-item {
  padding: 0 2.5rem;
}

.container .md-layout-item .single-item .item-icon {
  padding: 1.25rem;
  background-color: blue;
  border-radius: 0.313rem;
}

.container .md-layout-item img {
  width: 31.25rem;
  /* border: 1px solid gray; */
  border-radius: 0.313rem;
}

#contact {
  display: flex;
  justify-content: center;
}

#contact .md-button {
  color: white !important;
  background-color: #27A11A;
  width: 400px;
  height: 60px;
  border-radius: 5px;
}

#contact .md-button .md-button-content {
  font-size: 1.3vw;
}

#contact .md-button .md-icon {
  color: white !important;
  margin-top: -4px;
}

#footer {
  display: flex;
  justify-content: center;
  gap: 40px;
  background-color: #43B3CC;
}

#footer .footer-content {
  display: flex;
  gap: 10px;
}

#footer .footer-content p, #footer .footer-content .md-icon {
  color: white !important;
}

@media (max-width: 1195px) {

}

@media (max-width: 1450px) {
  .container {
    margin: 0 9.375rem;
  }

  .md-toolbar {
    padding: 0 9.375rem;
  }
}

@media (max-width: 553px) {
  .container {
    margin: 1.25rem;
  }

  #footer .footer-content {
    gap: 0
  }

  #footer .footer-content p, #footer .footer-content i {
    font-size: 0.438rem !important;
  }
}
</style>

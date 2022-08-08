<template>
  <div style="background-color: #ebedf0">
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
          <div class="md-layout-item right reverse" v-if="idx % 2 == 0" style="margin-top: 2.188rem">
            <div v-for="(val, i) in feature.featureList" :key="i" class="item-wrapper">
              <div class="single-item md-layout-item">
                <img src="/payroll.png" style="display: flex !important; justify-content: center; color: white" alt="">
              </div>
              <p style="text-align: center; font-size: 0.625rem">{{ val.label }}</p>
            </div>
          </div>
          <div v-if="idx % 2 == 0" class="reverse md-layout-item">
            <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
          </div>

          <div v-if="idx % 2 !== 0" class="md-layout-item right">
            <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
          </div>
          <div class="md-layout-item not-reverse" v-if="idx % 2 !== 0">
            <div v-for="(val, i) in feature.featureList" :key="i" class="item-wrapper">
              <div class="single-item md-layout-item">
                <img src="/payroll.png" style="display: flex !important; justify-content: center; color: white" alt="">
              </div>
              <p style="text-align: center; font-size: 0.625rem">{{ val.label }}</p>
            </div>
          </div>
        </div>
      </div>

      <div id="carousel" class="section">
        <vueper-slides class="no-shadow" transition-speed="250">
          <vueper-slide
            v-for="(val, i) in slides"
            :key="i"
            :image="val.image" 
          />
        </vueper-slides>
        <!-- <vueper-slides class="no-shadow" transition-speed="250"
          :class="{ 'offset-slide--first': firstSlide, 'offset-slide--last': lastSlide }"
          @before-slide="beforeSlide"
          :visible-slides="3"
          :slide-ratio="1/4"
          :dragging-distance="35"
          :arrows-outside="false"
          show-multiple-slides)>
          <vueper-slide
            v-for="(slide, i) in slides" :key="i" :title="(i + 1).toString()"
          />
        </vueper-slides> -->
      </div>

      <div class="section" id="vidio">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/N47NrKoR3BQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
      
      <div id="contact" class="section">
        <md-button href="https://wa.me/+6282136446350" target="_blank" class="md-primary">
          <md-icon>whatsapp</md-icon>
          0821-3644-6350
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
              {
              icon: "event",
              label: "Timesheet",
              },
              {
                icon: "sticky_note_2",
                label: "Perijinan",
              },
              {
                icon: "assignment",
                label: "Data Karyawan",
              },
              {
                icon: "edit_document",
                label: "Data Kontrak",
              },
              {
                icon: "calendar_month",
                label: "Kalender",
              },
              {
                icon: "backup_table",
                label: "Dokumen Karyawan",
              },
          ],
        },
        {
          name: "Penggajian",
          image: "feature-payroll.png",
          featureList: [
              {
                icon: "monetization_on",
                label: "Data Gaji",
              },
              {
                icon: "post_min",
                label: "Potongan Gaji",
              },
              {
                icon: "post_add",
                label: "Bonus",
              },
              {
                icon: "home",
                label: "THR",
              },
              {
                icon: "home",
                label: "Keuangan",
              },
          ],
        },
        {
          name: "Laporan",
          image: "feature-report.png",
          featureList: [
            {
              icon: "home",
              label: "Penggajian",
            },
            {
              icon: "",
              label: "Keuangan",
            },
            {
              icon: "home",
              label: "Kehadiran",
            },
            {
              icon: "home",
              label: "Kontrak",
            }
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
  width: 80%;
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
  gap: 10px;
}

.container .md-layout-item.right.reverse {
  display: grid;
  justify-content: flex-end;
  gap: 10px;
  grid-template-columns: 1fr 1fr 1fr;
}

.container .md-layout-item.not-reverse{
  margin-top: 8.125rem;
  display: grid;
  justify-content: flex-end;
  gap: 10px;
  grid-template-columns: 1fr 1fr 1fr;
}

.container .md-layout-item .item-wrapper {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.container .md-layout-item .item-wrapper p {
  display: block;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.container .md-layout-item .single-item {
  width: 50px;
  background-color: blue;
  min-height: 50px;
  max-height: 50px;
  border-radius: 0.313rem;
  background: blue;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container .md-layout-item .single-item img {
  width: 20px;
  justify-content: center;
  display: flex;
  align-items: center;
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
  width: 14.83vw;
  height: 3.125rem;
  border-radius: 5px;
}

#contact .md-button .md-button-content {
  font-size: 1.3vw;
}

#contact .md-button .md-icon {
  color: white !important;
  margin-top: -4px;
  font-size: 1.3vw !important;
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

.vueperslide, .vueperslide__image{
  background-size: 350px;
  background-repeat: no-repeat;
}

.vueperslides__inner {
  width: 600px;
  max-width: 100%;
  margin: auto;
}

.vueperslides__arrows button {
  color: black;
}

.vueperslides__arrow svg {
  width: 2.5em;
}

.vueperslides__bullets button {
  display: none;
}

#vidio {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%; 
  height: 0;
}

#vidio iframe {
  position: absolute;
  top:0;
  left: 0;
  width: 100%;
  height: 100%;
}

@media (max-width: 1195px) {

}

@media (max-width: 1575px) {
  .container {
    margin: 0 9.375rem;
  }

  .md-toolbar {
    padding: 0 9.375rem;
  }
}

@media (max-width: 1244px) {
  .container .md-layout-item .single-item {
    /* padding: 0 1.563rem; */
  }

  #contact .md-button {
    height: 2.5rem;
  }
}

@media (max-width: 1063px) {
  .container .md-layout-item .single-item {
    /* padding: 0 0.938rem; */
  }
}

@media (max-width: 1120px) {
  #contact .md-button .md-icon {
    margin-top: -2px;
  }
}

@media (max-width: 946px) {
  .container {
    margin: 0 1.25rem;
  }

  #contact .md-button {
    width: 24.83vw;
  }

  #contact .md-button .md-button-content, #contact .md-button .md-button-content i {
    font-size: 2.3vw !important;
  }
}

@media (max-width: 694px) {
  .container .md-layout-item .single-item .img {
    padding: 0.938rem;
    font-size: 0.938rem !important;
  }

  #contact .md-button {
    width: 25.83vw;
  }
}

@media (max-width: 667px) {
  #banner {
    height: 18.75rem;
  }

  .md-layout {
    flex-flow: column;
  }

  .md-layout-item.right.reverse {
    order: 2;
    /* justify-content: center; */
    display: grid;
    justify-content: flex-end;
    gap: 10px;
    grid-template-columns: 1fr 1fr 1fr;
  }

  .md-layout-item.reverse {
    order: 1;
    justify-content: center;
  }

  .md-layout-item.right {
    justify-content: center;
  }

  .md-layout-item {
    justify-content: center;
    margin-top: 0 !important;
  }

  .section {
    padding-top: 0.625rem;
    padding-bottom: 0.625rem;
  }

  .vueperslide, .vueperslide__image{
    background-size: 300px;
  }

  #contact .md-button .md-icon {
    margin-right: -6px;
  }
}

@media (max-width: 560px) {
  .vueperslide, .vueperslide__image{
    background-size: 250px;
  }
}

@media (max-width: 553px) {
  .container {
    margin: 1.25rem;
  }

  .md-toolbar {
    display: none;
  }

  #banner {
    height: 14.063rem;
    padding-top: 1.25rem;
  }

  #footer .footer-content {
    gap: 0
  }

  #footer .footer-content p, #footer .footer-content i {
    font-size: 0.438rem !important;
  }
}

@media (max-width: 465px) {
  #contact .md-button {
    width: 35.83vw;
  }

  #contact .md-button .md-button-content, #contact .md-button .md-button-content i {
    font-size: 3.3vw !important;
  }

  .vueperslide, .vueperslide__image{
    background-size: 200px;
  }

  .container .md-layout-item .single-item {
    width: 35px;
    min-height: 35px;
    max-height: 35px;
  }
}

@media (max-width: 420px) {
  #banner {
    height: 11.563rem;
  }
}

@media (max-width: 373px) {
  .vueperslide, .vueperslide__image{
    background-size: 150px;
  }
}

/*  */
/* .vueperslides__arrow {color: #333;}
.vueperslides__bullet {border-color: #E73C7E;box-shadow: none;}

.vueperslide {
  color: #fff;
  background: linear-gradient(-45deg, #EE7752, #E73C7E, #23A6D5, #23D5AB);
  transition: .3s ease-in-out;
  opacity: 0.3;
  filter: blur(4px);
  transform: scale(0.8);
}

.vueperslide --active {
  opacity: 1 !important;
  transform: scale(1);
  filter: blur(0);
}

.vueperslide __title {
  font-size: 7em;
  opacity: 0.6;
}

.offset-slide--first .vueperslides__track-inner {
  transform: translate3d(33.333%, 0, 0) !important;
}

.offset-slide--last .vueperslides__track-inner {
  transform: translate3d(-133.33%, 0, 0) !important;
}

p {
  position: absolute;
  top: 5px;
  right: 5px;
  z-index: 10;
} */
</style>

<template>
  <div style="background-color: white">
    <md-toolbar class="md-accent" md-elevation="1">
      <h3 class="md-title">Belivine</h3>
      <md-button>Beranda</md-button>
      <md-button>Fitur</md-button>
      <md-button>Kontak</md-button>
    </md-toolbar>
    <div class="banner">
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
      <div class="about section">
        <h1>Apa itu Belivine?</h1>
        <p>
          Belivine merupakan Human Resource Management System yang akan membantu
          mempermudah pembisnis atau perusahaan dalam mengoleola data karyawan
        </p>
      </div>

      <div class="feature section">
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
      
    </div>
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      screenWidth: 0,
      features: [
        {
          name: "HR",
          image: "feature-hr.png",
          featureList: [
            [
              {
              icon: "home",
              label: "Timesheet",
              },
              {
                icon: "",
                label: "Perijinan",
              },
            ],
            [
              {
                icon: "home",
                label: "Data Karyawan",
              },
              {
                icon: "home",
                label: "Data Kontrak",
              }
            ],
            [
              {
                icon: "home",
                label: "Kalender",
              },
              {
                icon: "home",
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
                icon: "home",
                label: "Data Gaji",
              },
              {
                icon: "home",
                label: "Potongan Gaji",
              },
            ],
            [
              {
                icon: "home",
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
              label: "Timesheet",
              },
              {
                icon: "",
                label: "Perijinan",
              },
            ],
            [
              {
                icon: "home",
                label: "Data Karyawan",
              },
              {
                icon: "home",
                label: "Data Kontrak",
              }
            ],
            [
              {
                icon: "home",
                label: "Kalender",
              },
              {
                icon: "home",
                label: "Dokumen Karyawan",
              },
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

.banner {
  height: 31.25rem;
  width: 100%;
  background-color: #1165ad;
  padding-top: 4.688rem;
  color: white;
}

.banner .banner-left h1 {
  font-size: 2.5rem;
}

.banner-right {
  margin-left: 3.125rem;
}

.banner .banner-right img {
  width: 18.75rem;
}

.section {
  padding-top: 50px;
  padding-bottom: 50px;
}

.container {
  margin-left: 18.75rem;
  margin-right: 18.75rem;
}

.about {
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

@media (max-width: 1450px) {
  .container {
    margin: 0 9.375rem;
  }
}
</style>

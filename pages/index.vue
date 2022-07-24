<template>
  <div style="background-color: white">
    <md-toolbar class="md-accent" md-elevation="1">
      <h3 class="md-title">Belivine</h3>
      <md-button>Beranda</md-button>
      <md-button>Fitur</md-button>
      <md-button>Kontak</md-button>
    </md-toolbar>
    <div class="container">
      <div class="about">
        <h1>Apa itu Belivine?</h1>
        <p>
          Belivine merupakan Human Resource Management System yang akan membantu
          mempermudah pembisnis atau perusahaan dalam mengoleola data karyawan
        </p>
      </div>
      <div
        class="md-layout md-gutter"
        v-for="(feature, idx) in features"
        :key="idx"
      >
        <div class="md-layout-item md-size-15"></div>
        <div v-if="idx % 2 == 0" class="md-layout-item right md-size-35">
          <div
            class="single-item"
            v-for="(list, index) in feature.featureList"
            :key="index"
          >
            <md-icon class="item-icon" style="dispay: flex">{{
              list.icon
            }}</md-icon>
            <p style="">{{ list.label }}</p>
          </div>
        </div>
        <div v-if="idx % 2 == 0" class="md-layout-item md-size-35">
          <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
        </div>
        <div class="md-layout-item md-size-15"></div>

        <div v-if="idx % 2 !== 0" class="md-layout-item right">
          <img :src="require(`~/assets/images/${feature.image}`)" alt="" />
        </div>
        <div v-if="idx % 2 !== 0" class="md-layout-item">
          <div
            class="single-item"
            v-for="(list, index) in feature.featureList"
            :key="index"
          >
            <md-icon class="item-icon" style="dispay: block">{{
              list.icon
            }}</md-icon>
            <p style="">{{ list.lable }}</p>
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
      features: [
        {
          name: "HR",
          image: "feature-hr.png",
          featureList: [
            {
              icon: "home",
              label: "Timesheet",
            },
            {
              icon: "",
              label: "Perijinan",
            },
            {
              icon: "home",
              label: "Kalender",
            },
            {
              icon: "home",
              label: "Data Karyawan",
            },
            {
              icon: "home",
              label: "Data Kontrak",
            },
            {
              icon: "home",
              label: "Dokumen Karyawan",
            },
          ],
        },
        {
          name: "Penggajian",
          image: "feature-payroll.png",
          featureList: [
            {
              icon: "home",
              label: "Data Gaji",
            },
            {
              icon: "home",
              label: "Potongan Gaji",
            },
            {
              icon: "home",
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
              label: "Kehadiran",
            },
            {
              icon: "home",
              label: "Kontrak",
            },
            {
              icon: "home",
              label: "Keuangan",
            },
          ],
        },
      ],
    };
  },
};
</script>

<style>
.md-accent .md-title {
  flex: 1;
}

.container {
  margin: 0 25px 0 25px;
}

.container .md-layout {
  margin: 50px 0px;
}

.container .md-layout-item.right {
  display: flex;
  justify-content: flex-end;
}

.container .md-layout-item .single-item {
  padding: 0 40px;
}

.container .md-layout-item .single-item .item-icon {
  padding: 20px;
  background-color: blue;
  border-radius: 5px;
}

.container .md-layout-item img {
  width: 500px;
  /* border: 1px solid gray; */
  border-radius: 5px;
}
</style>

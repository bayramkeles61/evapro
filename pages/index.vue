<template>
  <section class="dashboard">
    <!-- Stats Cards -->
    <div class="cards-row">
      <div class="stats-cards" v-for="stats in statsCards" :key="stats.title">
        <StatsCard>
          <div class="card-content" slot="stats-header">
            <div class="stats-header">
              <svg class="icon" :class="`icon-${stats.type}`">
                <use :href="stats.icon" />
              </svg>
              <span class="title" :class="`title-${stats.type}`">{{
                stats.title
              }}</span>
            </div>
            <div class="card-footer" slot="footer">
              <div class="card-footer-left">
                <div class="card-left-top">
                  {{ stats.valueLeft }}
                </div>
                <div class="card-left-bottom">
                  {{ stats.valueTextLeft }}
                </div>
              </div>
              <div class="card-footer-right">
                <div class="card-right-top">
                  {{ stats.valueRight }}
                </div>
                <div class="card-right-bottom">
                  {{ stats.valueTextRight }}
                </div>
              </div>
            </div>
          </div>
        </StatsCard>
      </div>
    </div>
    <!-- Stats Cards End -->
    <!-- Charts -->
    <!-- <client-only>
      <div class="cards-row">
        <div class="cards-wrapper">
          <div class="cards-content">
            <div class="cards-title">
              <span>Aylık Proje Sayısı</span>
            </div>
            <BarChart :chartdata="chartdata" :options="options" />
          </div>
        </div>
        <div class="cards-wrapper">
          <div class="cards-content">
            <div class="cards-title">
              <span>Sektörler</span>
            </div>
            <PieChart />
          </div>
        </div>
      </div>
    </client-only> -->
    <!-- Charts End -->
    <!-- Data Table Begin -->
    <div class="cards-row">
      <div class="cards-wrapper">
        <div class="cards-content">
          <span class="cards-title">Top 10 - Şirketler</span>
          <TopCompanies></TopCompanies>
        </div>
      </div>
      <div class="cards-wrapper">
        <div class="cards-content">
          <span class="cards-title">Top 10 - Şirketler</span>
          <CompanyProgress v-for="skill in skills" :key="skill.lang">
          </CompanyProgress>
        </div>
      </div>
    </div>
    <!-- Data Table End -->
  </section>
</template>

<script>
import StatsCard from "~/components/Cards/StatsCard.vue";
import BarChart from "~/components/Charts/BarChart";
import PieChart from "~/components/Charts/PieChart";
import TopCompanies from "~/components/DataTables/TopCompanies";
import CompanyProgress from "~/components/DataTables/CompanyProgress";
export default {
  components: {
    StatsCard,
    BarChart,
    PieChart,
    TopCompanies,
    CompanyProgress
  },

  data() {
    return {
      statsCards: [
        {
          type: "jury",
          icon: "#icon-jury",
          title: "Jüri",
          valueLeft: "5000",
          valueRight: "1500",
          valueTextLeft: "Akademisyen",
          valueTextRight: "Sektör Uzmanı"
        },
        {
          type: "company",
          icon: "#icon-company",
          title: "Toplam Şirket",
          valueLeft: "2500",
          valueRight: "300",
          valueTextLeft: "Aktif",
          valueTextRight: "Pasif"
        },
        {
          type: "project",
          icon: "#icon-project",
          title: "Toplam Proje",
          valueLeft: "10830",
          valueRight: "5687",
          valueTextLeft: "Devam ediyor",
          valueTextRight: "Tamamlandı"
        },
        {
          type: "evaluation",
          icon: "#icon-evaluation",
          title: "Toplam Değerlendirme",
          valueLeft: "5870",
          valueRight: "2515",
          valueTextLeft: "Test1",
          valueTextRight: "Test2"
        }
      ],


      skills: [
        { lang: "BestBro", percent: 90, color: "#ec407a" },
        { lang: "Amaxon", percent: 76, color: "#f4511e" },
        { lang: "Texla", percent: 84, color: "#512da8" },
        { lang: "Citkoen", percent: 94, color: "#f57c00" },
        { lang: "Mixrosoft", percent: 93, color: "#0288d1" },
        { lang: "Meicedes", percent: 87, color: "#388e3c" },
        { lang: "Sylicon", percent: 90, color: "#ec407a" },
        { lang: "Axple", percent: 76, color: "#f4511e" },
        { lang: "Samsunx", percent: 84, color: "#512da8" },
        { lang: "Noxia", percent: 94, color: "#f57c00" }
      ]
    };
  },
};
</script>

<style scoped>
.dashboard {
  background-color: var(--light);
  width: 100%;
  height: 100%;
  padding: 1.5rem;
}

.cards-row {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.cards-wrapper {
  padding: 1rem;
  width: 50%;
}

.cards-content {
  padding: 1rem;
  border-radius: 16px;
  background-color: var(--white);
  box-shadow: 0px 0px 25px 5px var(--gray-shadow);
}

.cards-title {
  background-color: var(--white);
  height: 100%;
  padding-bottom: 1rem;
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--blue-dark);

  display: flex;
  justify-content: center;
  align-items: center;
}

/*********** STATS ***********/
.stats-cards {
  width: 25%;
  display: flex;
  flex-wrap: wrap;
}

.card-content {
  background-color: var(--white);
  width: 100%;
  padding: 1.25rem;
  box-shadow: 0px 0px 25px 5px var(--gray-shadow);
  border-radius: 16px;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.stats-header {
  width: 100%;
  height: 50px;
  margin-bottom: 20px;

  display: flex;
  align-items: center;
}

.card-footer {
  color: var(--gray-dark);
  width: 100%;
  height: 200px;
  font-size: 21px;
  font-weight: 600;
  text-decoration: none solid rgb(73, 80, 87);
  text-align: center;
  word-spacing: 0px;

  display: flex;
}

.card-footer-left {
  width: 50%;
  height: 100%;
  border-right: 1px solid var(--gray-light);

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card-left-top {
  width: 100%;
  height: 30px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.card-left-bottom {
  width: 100%;
  height: 20px;
  margin: 4px;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none solid rgb(108, 117, 125);
  color: var(--gray);
  background-position: 0% 0%;
  word-spacing: 0px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.card-footer-right {
  width: 50%;
  height: 100%;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card-right-top {
  width: 100%;
  height: 30px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.card-right-bottom {
  width: 100%;
  height: 20px;
  margin: 4px;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none solid rgb(108, 117, 125);
  color: var(--gray);
  background-position: 0% 0%;
  word-spacing: 0px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.icon {
  height: 50px;
  width: 50px;
  padding: 10px;
  border-radius: 5px;
}

.icon-jury {
  background-color: var(--blue);
  fill: var(--blue-dark);
}

.icon-company {
  background-color: var(--purple);
  fill: var(--purple-dark);
}

.icon-project {
  background-color: var(--green);
  fill: var(--green-dark);
}

.icon-evaluation {
  background-color: var(--cyan);
  fill: var(--cyan-dark);
}

.title {
  padding: 10px;
  font-size: 1rem;
  font-family: var(--font-sans-serif);
  font-weight: 600;
  letter-spacing: 1px;
}

.title-jury {
  color: var(--blue);
}

.title-company {
  color: var(--purple);
}

.title-project {
  color: var(--green);
}

.title-evaluation {
  color: var(--cyan);
}
/* STATS END */
@media screen and (max-width: 1200px) {
  .stats-cards {
    width: 50%;
  }

  .card-wrapper {
    width: 100%;
  }
}

@media screen and (max-width: 768px) {
  .stats-cards {
    width: 100%;
  }
}
</style>

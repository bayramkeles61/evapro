<template>
  <div>
    <h1>Şirket Sayfası</h1>
    <input
      type="text"
      class="data-cell"
      placeholder="Şirket adı giriniz.."
    />
    <table class="datatable-table">
      <thead>
        <tr>
          <th>Sıra</th>
          <th>Şirket Adı</th>
          <th>Şirket Sahibi</th>
          <th>Eposta</th>
          <th>Telefon</th>
          <th>Durum</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(company, index) in companies" :key="index">
          <td>{{ index + 1 }}</td>
          <td>{{ company.company_name }}</td>
          <td>{{ company.company_owner }}</td>
          <td>{{ company.company_email }}</td>
          <td>{{ company.company_phone }}</td>
          <td>{{ company.company_status }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import TheCompanies from "~/components/DataTables/TheCompanies";
export default {
  // asyncData -> Sayfa görüntülenmeden önce çalışır. Fetch ise sonra çalışır
  // mounted() {
  //   this.$axios
  //     .$get("https://ttoknokent.herokuapp.com/api/companies")
  //     .then((res) => {
  //       this.companies = res;
  //     });
  // },
 async asyncData({ $axios, redirect }) {
    const api ="https://ttoknokent.herokuapp.com/api/companies"
    try {
      const companies = await $axios.$get(api)
      return { companies}
    } catch (error) {
      redirect('/error')
    }
  },
  components: {
    TheCompanies,
  },
  data() {
    return {
      companies: [],
    };
  },
};
</script>

<style>
.datatable-table {
  display: table;
  max-width: 100%;
  width: 100%;
  border-spacing: 0;
  border-collapse: separate;
  caption-side: bottom;

  margin-bottom: 1rem;
  color: var(--gray);
  vertical-align: top;
  border-color: var(--light);
}

.datatable-table > :not(caption) > * > * {
  padding: 0.5rem;
  background-color: transparent;
  border-bottom-width: 1px;
  box-shadow: inset 0 0 0 9999px transparent;
}

tbody,
td,
tfoot,
th,
thead,
tr {
  border-color: inherit;
  border-style: solid;
  border-width: 0;
}

th,
td {
  white-space: nowrap;
}

td {
  display: table-cell;
  vertical-align: inherit;
  color: var(--blue-dark);
  color: #445573;
  font-weight: bold;
}

table {
  border-collapse: separate;
  text-indent: initial;
  border-spacing: 2px;
}

td:nth-child(1) {
  width: 10%;
  text-align: center;
}
td:nth-child(2) {
  width: 70%;
}
td:nth-child(3) {
  width: 20%;
  text-align: center;
}

@media (max-width: 800px) {
  td:nth-child(3),
  th:nth-child(3) {
    display: none;
  }
}
</style>

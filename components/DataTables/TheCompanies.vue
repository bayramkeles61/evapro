<template>
  <div>
    <!-- <h2>Şirketler ({{ companies.length }})</h2>
    <div class="row">
      <div class="row2">
        <validation-errors
          :errors="validationErrors"
          v-if="validationErrors"
        ></validation-errors>
        <form @submit.prevent="addCompany" class="form">
          <div class="form-group">
            <label for="title">İsim</label>
            <input
              v-model="company.company_name"
              type="text"
              class="form-control"
              id="title"
            />
          </div>
          <div class="form-group">
            <label for="company_owner">Açıklama</label>
            <textarea
              v-model="company.company_owner"
              class="form-control"
              id="description"
              rows="3"
            ></textarea>
          </div>
        </form>
      </div>
    </div> -->

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
          <td>
            <!-- <button @click="editCompany(company)" class="buton"></button>
            <button @click="deleteCompany(company)" class="buton"></button> -->
          </td>
        </tr>
      </tbody>
    </table>

    <!-- <nav>
      <ul class="pagination">
        <li
          :class="{ disabled: !pagination.prev_page_url }"
          @click.prevent="getCompanies(pagination.prev_page_url)"
          class="page-item"
        >
          <nuxt-link class="page-link" to="#">Geri dön</nuxt-link>
        </li>
        <li>
          <nuxt-link class="page-item disabled" to="#">
            Sayfa {{ pagination.current_page }} in-ın {{ pagination.last_page }}
          </nuxt-link>
        </li>
        <li
          :class="{ disabled: !pagination.next_page_url }"
          @click.prevent="getCompanies(pagination.next_page_url)"
          class="page-item"
        >
          <nuxt-link class="page-link" to="#">Sonraki</nuxt-link>
        </li>
      </ul>
    </nav> -->
  </div>
</template>


// <script>
// import axios from "axios";

// export default {
//   data() {
//     return {
//       companies: [],
//       company: {
//         company_id: "",
//         company_name: "",
//         company_owner: "",
//         company_email: "",
//         company_phone: "",
//         company_status: ""
//       },
//       pagination: {},
//       edit: false,
//       loading: true,
//       errored: false,
//       validationErrors: ""
//     };
//   },

//   created() {
//     this.getCompanies();
//   },

//   methods: {
//     getCompanies(page_url) {
//       page_url = page_url || "https://ttoknokent.herokuapp.com/api/companies";
//       axios
//         .get(page_url)
//         .then(response => {
//           this.companies = response.data.data;
//           this.makePagination(response.data);
//         })
//         .catch(error => {
//           console.log(error);
//           this.errored = true;
//         })
//         .finally(() => (this.loading = false));
//     },
//     makePagination(response) {
//       let pagination = {
//         current_page: response.current_page,
//         last_page: response.last_page,
//         prev_page_url: response.prev_page_url,
//         next_page_url: response.next_page_url
//       };
//       this.pagination = pagination;
//     },
//     deleteCompany(id) {
//       axios
//         .delete(`https://ttoknokent.herokuapp.com/api/companies/${id}`)
//         .then(response => {
//           this.getCompanies();
//           console.log(response);
//         })
//         .catch(error => console.log(error));
//     },
//     addCompany() {
//       if (this.edit === false) {
//         // Gönderi Ekleme
//         axios
//           .company("https://ttoknokent.herokuapp.com/api/companies", {
//             company_name: this.company.company_name,
//             company_owner: this.company.company_owner,
//             company_email: this.company.company_email,
//             company_phone: this.company.company_phone,
//             company_status: this.company.company_status
//           })
//           .then(response => {
//             this.company.company_name = "";
//             this.company.company_owner = "";
//             this.company.company_email = "";
//             this.company.company_phone = "";
//             this.company.company_status = "";
//             this.getCompanies();

//             console.log(response);
//           })
//           .catch(error => {
//             if (error.response.status === 422) {
//               this.validationErrors = error.response.data.errors;
//             }

//             console.log(error);
//           });
//       } else {
//         // Gönderi Düzenleme
//         axios
//           .put(
//             `https://ttoknokent.herokuapp.com/api/companies/${this.company.id}`,
//             {
//               company_name: this.company.company_name,
//               company_owner: this.company.company_owner,
//               company_email: this.company.company_email,
//               company_phone: this.company.company_phone,
//               company_status: this.company.company_status
//             }
//           )
//           .then(response => {
//             this.company.company_name = "";
//             this.company.company_owner = "";
//             this.company.company_email = "";
//             this.company.company_phone = "";
//             this.company.company_status = "";
//             this.edit = false;
//             this.getCompanies();
//             console.log(response);
//           })
//           .catch(error => {
//             if (error.response.status === 422) {
//               this.validationErrors = error.response.data.errors;
//             }
//             console.log(error);
//           });
//       }
//     },
//     editCompany(company) {
//       this.edit = true;
//       this.company.company_id = company.company_id;
//       this.company.company_name = company.company_name;
//       this.company.company_owner = company.company_owner;
//       this.company.company_email = company.company_email;
//       this.company.company_phone = company.company_phone;
//       this.company.company_status = company.company_status;
//     }
//   }
// };
// </script>
<script>
export default {
  // asyncData -> Sayfa görüntülenmeden önce çalışır. Fetch ise sonra çalışır
  async asyncData({ $axios, redirect }) {
    const api ="https://ttoknokent.herokuapp.com/api/companies"

    try {
      const companies = await $axios.$get(api)
      return { companies}
    } catch (error) {
      redirect('/error')
    }
  }
}
</script>

<style scoped>
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

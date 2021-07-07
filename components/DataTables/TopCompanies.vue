<template>
  <table class="datatable-table">
    <thead>
      <tr>
        <th>Sıra</th>
        <th>Şirket</th>
        <th>Puan</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>BestBro</td>
        <td>85</td>
      </tr>
      <tr>
        <td>2</td>
        <td>Amaxon</td>
        <td>82</td>
      </tr>
      <tr>
        <td>3</td>
        <td>Texla</td>
        <td>80</td>
      </tr>
      <tr>
        <td>4</td>
        <td>Amaxon</td>
        <td>77</td>
      </tr>
      <tr>
        <td>5</td>
        <td>Mixrosoft</td>
        <td>74</td>
      </tr>
      <tr>
        <td>6</td>
        <td>Amaxon</td>
        <td>72</td>
      </tr>
      <tr>
        <td>7</td>
        <td>Sylicon</td>
        <td>70</td>
      </tr>
      <tr>
        <td>8</td>
        <td>Axple</td>
        <td>69</td>
      </tr>
      <tr>
        <td>9</td>
        <td>Samsunx</td>
        <td>67</td>
      </tr>
      <tr>
        <td>10</td>
        <td>Noxia</td>
        <td>65</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {};
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

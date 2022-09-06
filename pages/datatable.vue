<template>
  <section>
    <b-select v-model="perPage" :disabled="!isPaginated">
                <option value="5">5 per page</option>
                <option value="10">10 per page</option>
                <option value="15">15 per page</option>
                <option value="20">20 per page</option>
            </b-select>

      <b-table
          :data="data"
          :paginated="isPaginated"
          :per-page="perPage"
          :current-page.sync="currentPage"
          :pagination-simple="isPaginationSimple"
          :pagination-position="paginationPosition"
          :default-sort-direction="defaultSortDirection"
          :pagination-rounded="isPaginationRounded"
          :sort-icon="sortIcon"
          :sort-icon-size="sortIconSize"
          default-sort="user.first_name"
          aria-next-label="Next page"
          aria-previous-label="Previous page"
          aria-page-label="Page"
          aria-current-label="Current page"
          :page-input="hasInput"
          :pagination-order="paginationOrder"
          :page-input-position="inputPosition"
          :debounce-page-input="inputDebounce">

          <b-table-column field="id" label="ID" width="40" sortable numeric v-slot="props">
              {{ props.row.id }}
          </b-table-column>

          <b-table-column field="user.first_name" label="First Name" sortable v-slot="props">
              {{ props.row.first_name }}
          </b-table-column>

          <b-table-column field="user.last_name" label="Last Name" sortable v-slot="props">
              {{ props.row.last_name }}
          </b-table-column>

          <b-table-column field="date" label="Date" sortable centered v-slot="props">
              <span class="tag is-success">
                  {{ new Date(props.row.date).toLocaleDateString() }}
              </span>
          </b-table-column>

          <b-table-column label="Gender" v-slot="props">
              <span>
                  <b-icon pack="fas"
                      :icon="props.row.gender === 'Male' ? 'mars' : 'venus'">
                  </b-icon>
                  {{ props.row.gender }}
              </span>
          </b-table-column>

      </b-table>
  </section>
</template>

<script>


  export default {
      data() {
          return {
            data:  [
                  { 'id': 1, 'first_name': 'Jesse', 'last_name': 'Simmons', 'date': '2016-10-15 13:43:27', 'gender': 'Male' },
                  { 'id': 2, 'first_name': 'John', 'last_name': 'Jacobs', 'date': '2016-12-15 06:00:53', 'gender': 'Male' },
                  { 'id': 3, 'first_name': 'Tina', 'last_name': 'Gilbert', 'date': '2016-04-26 06:26:28', 'gender': 'Female' },
                  { 'id': 4, 'first_name': 'Clarence', 'last_name': 'Flores', 'date': '2016-04-10 10:28:46', 'gender': 'Male' },
                  { 'id': 5, 'first_name': 'Anne', 'last_name': 'Lee', 'date': '2016-12-06 14:38:38', 'gender': 'Female' },
                  { 'id': 6, 'first_name': 'Jesse', 'last_name': 'Simmons', 'date': '2016-10-15 13:43:27', 'gender': 'Male' },
                  { 'id': 7, 'first_name': 'John', 'last_name': 'Jacobs', 'date': '2016-12-15 06:00:53', 'gender': 'Male' },
                  { 'id': 8, 'first_name': 'Tina', 'last_name': 'Gilbert', 'date': '2016-04-26 06:26:28', 'gender': 'Female' },
                  { 'id': 9, 'first_name': 'Clarence', 'last_name': 'Flores', 'date': '2016-04-10 10:28:46', 'gender': 'Male' },
                  { 'id': 10, 'first_name': 'Anne', 'last_name': 'Lee', 'date': '2016-12-06 14:38:38', 'gender': 'Female' },
              ],
              isPaginated: true,
              isPaginationSimple: false,
              isPaginationRounded: false,
              paginationPosition: 'bottom',
              defaultSortDirection: 'asc',
              sortIcon: 'arrow-up',
              sortIconSize: 'is-small',
              currentPage: 1,
              perPage: 5,
              hasInput: false,
              paginationOrder: '',
              inputPosition: '',
              inputDebounce: ''
          }
      }
  }
</script>

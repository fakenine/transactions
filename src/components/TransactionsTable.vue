<template>
  <div class="p-5">
    <b-table
      hover
      :items="itemsProvider"
      :fields="fields"
      selectable
      :select-mode="selectMode"
      @row-selected="onRowSelected"
      :no-provider-sorting="true"
    >
      <template #cell(amount)="data">
        {{ data.value }}
        <b-icon v-if="data.item.credit == 'true'" icon="triangle-fill" class="payment-triangle credit-triangle"></b-icon>
        <b-icon v-else icon="triangle-fill" flip-v class="payment-triangle debit-triangle"></b-icon>
      </template>

      <template #head(attachements)>
        <b-icon icon="paperclip"></b-icon>
      </template>

      <template #cell(attachements)="data">
        <b-icon icon="paperclip"></b-icon>
        {{ data.item.attachements.length }}
      </template>

      <template #cell(show_details)="row">
        <b-button size="sm" @click="row.toggleDetails" class="mr-2">
          {{ row.detailsShowing ? 'Hide' : 'Show'}} Details
        </b-button>
      </template>

      <template #row-details="row">
        <b-card>
          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Date:</b></b-col>
            <b-col>{{ row.item.created_at }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Counterparty name:</b></b-col>
            <b-col>{{ row.item.counterparty_name }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Amount:</b></b-col>
            <b-col>{{ row.item.amount }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Currency:</b></b-col>
            <b-col>{{ row.item.currency }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Operation type:</b></b-col>
            <b-col>{{ row.item.operation_type }}</b-col>
          </b-row>

          <b-row class="mb-2">
            <b-col sm="3" class="text-sm-right"><b>Attachements:</b></b-col>
            <b-col>
              <ul>
                <li v-for="attachement in row.item.attachements" :key="attachement.url">                
                  <b-link :href="attachement.url">Download</b-link>
                </li>
              </ul>
            </b-col>
          </b-row>

          <b-button size="sm" @click="row.toggleDetails">Hide Details</b-button>
        </b-card>
      </template>
    </b-table>
  </div>
</template>

<script>
  import axios from 'axios';
  import dayjs from 'dayjs';

  export default {
    name: 'TransactionsTable',
    data() {
      return {
        fields: [
          {
            key: 'created_at',
            sortable: true,
            label: 'DD-MM-YYYY',
            formatter: value => {
              return dayjs(value).format('DD-MM-YYYY')
            }
          },
          { key: 'counterparty_name', sortable: true },
          { key: 'operation_type', sortable: true, label: 'Payment type' },
          { key: 'amount', sortable: true },
          'attachements',
          'show_details'
        ],
        selectMode: 'range',
        selected: []
      }
    },
    methods: {
      itemsProvider: function() {
        const promise = axios.get('/transactions')

        // Must return a promise that resolves to an array of items
        return promise.then(data => {
          // Pluck the array of items off our axios response
          const items = data.data[0].transactions
          // Must return an array of items or an empty array if an error occurred
          return items || []
        })
      },
      onRowSelected: function(items) {
        this.selected = items
      },
    }
  }
</script>

<style lang="scss">
  .payment-triangle {
    font-size: 10px;
  }

  .credit-triangle {
    color: lightblue;
  }

  .debit-triangle {
    color: red;
  }
</style>
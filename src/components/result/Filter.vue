<template>
    <div class="sider">
      <div class="sider-content-title">Sort by</div>
      <a-select
        placeholder="Automatic tokenization"
        style="width: 90%;"
        v-model:value="sortVal"
        :options="options"
        @change="handleChange"
        >   
        </a-select>
      <div class="sider-content-title">Range of Date</div>
      <a-space direction="vertical">
        <a-range-picker
          :placeholder="['Start Date', 'End Date']"
          @change="rangeChange"
          v-model:value="showDateTime"
        />
      </a-space>
      <div class="sider-content-title">Inventor</div>
      <a-input style="width: 90%"  v-model:value="inventor" placeholder="Inventor name" @change="inventorChange"/>
      <div class="sider-content-title">Assignee</div>
      <a-input style="width: 90%"  v-model:value="assignee" placeholder="Assignee name" @change="assigneeChange"/>
      <div class="sider-content-title">Key words</div>
      <a-input style="width: 90%"  v-model:value="key" placeholder="Key words" @change="keyChange"/>
      <div class="clear" @click="clear">Clear All</div>
    </div>   
  </template>
  <script>
  import { ref } from 'vue';
  export default {
    data() {
      return {
        showDateTime: null
      }
    },
    setup() {
        const options = ref([
            {
                value: 'Relevance',
                label: 'Relevance',
            },
            {
                value: 'Latest',
                label: 'Latest',
            },
            {
                value: 'Oldest',
                label: 'Oldest',
            },
        ]);
        const inventor = ref('');
        const assignee = ref('');
        const key = ref('');
        const sortVal = ref(null);
        return {
            inventor,
            assignee,
            key,
            sortVal,
            options
        };
    },
    methods: {
        rangeChange(date, dateRange) {
            this.inputDisabled = dateRange.length && dateRange[0] && dateRange[1] ? true : false;
        },
        inputChange(inputVal) {
            console.log('iii')
        },
        assigneeChange(val) {
        },
        keyChange(val) {
        },
      clear() {
        this.inventor = '';
        this.assignee = '';
        this.key = '';
        this.showDateTime = null;
      }
    }
  }
  </script>
  <style>
  .sider {
    padding: 0 10px 0 20px;
    .ant-space {
        width: 90% !important;
    }
    .ant-picker {
        width: 100% !important;
    }
    .sider-content-title {
      font-size: 16px;
      font-weight: 500;
      color: #3A3C49;
      margin: 20px 0 10px;
    }
    .clear {
      color: #0089C6;
      font-size: 16px;
      margin-top: 40px;
      text-decoration: underline;
      cursor: pointer;
    }  
  }
  </style>
  
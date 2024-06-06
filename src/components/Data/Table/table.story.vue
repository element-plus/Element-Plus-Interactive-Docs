<script setup lang="ts">
import { ref } from 'vue'
import sizeOptions from '@constants/sizeOptions'
import { alignOptions } from './constants'

/** Basic-Table */
const tableData = ref([
  {
    name: 'John Doe',
    age: 28,
    gender: 'Male',
    country: 'USA',
    city: 'New York',
    occupation: 'Engineer',
    education: 'Bachelor',
    language: 'English',
    hobbies: 'Basketball',
    income: 8000,
    email: 'johndoe@example.com',
    phone: '1234567890',
    address: '123 Main St',
    registrationDate: '2022-01-01',
    remarks: 'None',
    status: 'Active',
  },
  {
    name: 'Jane Smith',
    age: 32,
    gender: 'Female',
    country: 'Canada',
    city: 'Toronto',
    occupation: 'Doctor',
    education: 'Master',
    language: 'English',
    hobbies: 'Reading',
    income: 10000,
    email: 'janesmith@example.com',
    phone: '9876543210',
    address: '456 Elm St',
    registrationDate: '2022-02-15',
    remarks: 'Likes to travel',
    status: 'Active',
  },
  {
    name: 'Michael Johnson',
    age: 35,
    gender: 'Male',
    country: 'Australia',
    city: 'Sydney',
    occupation: 'Teacher',
    education: 'PhD',
    language: 'English',
    hobbies: 'Hiking',
    income: 6000,
    email: 'michaeljohnson@example.com',
    phone: '4567891230',
    address: '789 Oak St',
    registrationDate: '2022-03-10',
    remarks: 'Enjoys cooking',
    status: 'Inactive',
  },
  {
    name: 'Emily Davis',
    age: 29,
    gender: 'Female',
    country: 'UK',
    city: 'London',
    occupation: 'Designer',
    education: 'Bachelor',
    language: 'English',
    hobbies: 'Painting',
    income: 7500,
    email: 'emilydavis@example.com',
    phone: '7891234560',
    address: '321 Pine St',
    registrationDate: '2022-04-05',
    remarks: 'Loves photography',
    status: 'Active',
  },
  {
    name: 'David Wilson',
    age: 31,
    gender: 'Male',
    country: 'Germany',
    city: 'Berlin',
    occupation: 'Developer',
    education: 'Master',
    language: 'German',
    hobbies: 'Gaming',
    income: 9000,
    email: 'davidwilson@example.com',
    phone: '0123456789',
    address: '987 Cedar St',
    registrationDate: '2022-05-20',
    remarks: 'Plays guitar',
    status: 'Active',
  },
  {
    name: 'Sophia Martinez',
    age: 27,
    gender: 'Female',
    country: 'Spain',
    city: 'Madrid',
    occupation: 'Writer',
    education: 'Bachelor',
    language: 'Spanish',
    hobbies: 'Dancing',
    income: 5500,
    email: 'sophiamartinez@example.com',
    phone: '2345678901',
    address: '654 Maple St',
    registrationDate: '2022-06-15',
    remarks: 'Enjoys hiking',
    status: 'Inactive',
  },
  {
    name: 'Daniel Anderson',
    age: 33,
    gender: 'Male',
    country: 'France',
    city: 'Paris',
    occupation: 'Manager',
    education: 'Master',
    language: 'French',
    hobbies: 'Photography',
    income: 7000,
    email: 'danielanderson@example.com',
    phone: '3456789012',
    address: '876 Walnut St',
    registrationDate: '2022-07-10',
    remarks: 'Loves to travel',
    status: 'Active',
  },
  {
    name: 'Olivia Taylor',
    age: 30,
    gender: 'Female',
    country: 'Italy',
    city: 'Rome',
    occupation: 'Architect',
    education: 'PhD',
    language: 'Italian',
    hobbies: 'Singing',
    income: 8500,
    email: 'oliviataylor@example.com',
    phone: '4567890123',
    address: '543 Birch St',
    registrationDate: '2022-08-25',
    remarks: 'Plays piano',
    status: 'Active',
  },
  {
    name: 'Isabella Lee',
    age: 28,
    gender: 'Female',
    country: 'South Korea',
    city: 'Seoul',
    occupation: 'Marketing',
    education: 'Bachelor',
    language: 'Korean',
    hobbies: 'Traveling',
    income: 6000,
    email: 'isabellalee@example.com',
    phone: '6789012345',
    address: '432 Pine St',
    registrationDate: '2022-10-15',
    remarks: 'Enjoys playing piano',
    status: 'Active',
  },
  {
    name: 'Ethan Clark',
    age: 29,
    gender: 'Male',
    country: 'Brazil',
    city: 'Rio de Janeiro',
    occupation: 'Entrepreneur',
    education: 'Master',
    language: 'Portuguese',
    hobbies: 'Surfing',
    income: 9000,
    email: 'ethanclark@example.com',
    phone: '7890123456',
    address: '765 Elm St',
    registrationDate: '2022-11-10',
    remarks: 'Passionate about sports',
    status: 'Active',
  },
])

/** Basic-Table-Data */
const basicTableData = reactive({
  stripe: false,
  border: false,
  height: 500,
  fixed: false,
  sortable: false,
  size: 'default',
  sizeOptions,
  fit: true,
  showHeader: true,
  highlightCurrentRow: true,
  showOverflowTooltip: false,
  flexible: false,
  scrollbarAlwaysOn: false,
  showTableData: true,
  showSummary: false,
  emptyText: 'no data',
  alignOptions,
  resizable: true,
  align: 'left',
  headerAlign: 'left',
})

/** Basic-Table-Column */
const basicTableColumn = reactive([
  { label: 'Name', prop: 'name' },
  { label: 'Age', prop: 'age' },
  { label: 'Country', prop: 'country' },
  { label: 'City', prop: 'city' },
  { label: 'Occupation', prop: 'occupation' },
  { label: 'Education', prop: 'education' },
  { label: 'Language', prop: 'language' },
  { label: 'Hobbies', prop: 'hobbies' },
  { label: 'Income', prop: 'income' },
  { label: 'Email', prop: 'email' },
  { label: 'Phone', prop: 'phone' },
  { label: 'Address', prop: 'address' },
  { label: 'Registration Date', prop: 'registrationDate' },
  { label: 'Remarks', prop: 'remarks' },
  { label: 'Status', prop: 'status' },
])

/** tableRowClassName */
function tableRowClassName(row: any) {
  if (row.rowIndex === 1)
    return 'warning-row'
  else if (row.rowIndex === 3)
    return 'success-row'

  return ''
}

/** source */
const source = computed(() => {
  return `<script setup lang="ts">
const tableData = ref([
  {
    name: 'John Doe',
    age: 28,
    gender: 'Male',
    country: 'USA',
    city: 'New York',
    occupation: 'Engineer',
    education: 'Bachelor',
    language: 'English',
    hobbies: 'Basketball',
    income: 8000,
    email: 'johndoe@example.com',
    phone: '1234567890',
    address: '123 Main St',
    registrationDate: '2022-01-01',
    remarks: 'None',
    status: 'Active',
  },
  ...
])

const basicTableColumn = reactive([
  { label: 'Name', prop: 'name' },
  { label: 'Age', prop: 'age' },
  { label: 'Country', prop: 'country' },
  { label: 'City', prop: 'city' },
  { label: 'Occupation', prop: 'occupation' },
  { label: 'Education', prop: 'education' },
  { label: 'Language', prop: 'language' },
  { label: 'Hobbies', prop: 'hobbies' },
  { label: 'Income', prop: 'income' },
  { label: 'Email', prop: 'email' },
  { label: 'Phone', prop: 'phone' },
  { label: 'Address', prop: 'address' },
  { label: 'Registration Date', prop: 'registrationDate' },
  { label: 'Remarks', prop: 'remarks' },
  { label: 'Status', prop: 'status' },
])
<\/script>

<template>
  <el-table
        empty-text="${basicTableData.emptyText}"
        data="${basicTableData.showTableData ? 'tableData' : []}"
        stripe="${basicTableData.stripe}"
        border="${basicTableData.border}"
        row-class-name="tableRowClassName"
        height="${basicTableData.height}"
        style="width: 100%"
        size="${basicTableData.size}"
        fit="${basicTableData.fit}"
        show-header="${basicTableData.showHeader}"
        highlight-current-row="${basicTableData.highlightCurrentRow}"
        flexible="${basicTableData.flexible}"
        scrollbar-always-on="${basicTableData.scrollbarAlwaysOn}"
        show-summary="${basicTableData.showSummary}"
      >
        <el-table-column
          v-for="(item, index) in basicTableColumn"
          :key="index"
          min-width="120px"
          :label="item.label"
          :prop="item.prop"
          :fixed="item.label === 'Name' ? ${basicTableData.fixed} : false"
          :align="${basicTableData.align}"
          :show-overflow-tooltip="${basicTableData.showOverflowTooltip}"
          :sortable="${basicTableData.sortable}"
        >
          <template #header>
            <span>{{ item.label }}</span>
          </template>
          <template #default="scope">
            <span>{{ scope.row[item.prop] }}</span>
          </template>
        </el-table-column>
      </el-table>
</template>
`
})
</script>

<template>
  <Story
    title="Data/Table" icon="material-symbols-light:data-table-outline" :layout="{
      type: 'grid',
      width: '90%',
    }"
  >
    <Variant
      title="Basic Table"
      :source="source"
    >
      <el-table
        :empty-text="basicTableData.emptyText"
        :data="basicTableData.showTableData ? tableData : []"
        :stripe="basicTableData.stripe"
        :border="basicTableData.border"
        :row-class-name="tableRowClassName"
        :height="basicTableData.height"
        style="width: 100%"
        :size="basicTableData.size"
        :fit="basicTableData.fit"
        :show-header="basicTableData.showHeader"
        :highlight-current-row="basicTableData.highlightCurrentRow"
        :flexible="basicTableData.flexible"
        :scrollbar-always-on="basicTableData.scrollbarAlwaysOn"
        :show-summary="basicTableData.showSummary"
      >
        <el-table-column
          v-for="(item, index) in basicTableColumn"
          :key="index"
          min-width="120px"
          :label="item.label"
          :prop="item.prop"
          :fixed="item.label === 'Name' ? basicTableData.fixed : false"
          :align="basicTableData.align"
          :show-overflow-tooltip="basicTableData.showOverflowTooltip"
          :sortable="basicTableData.sortable"
        >
          <template #header>
            <span>{{ item.label }}</span>
          </template>
          <template #default="scope">
            <span>{{ scope.row[item.prop] }}</span>
          </template>
        </el-table-column>
      </el-table>
      <template #controls>
        <HstCheckbox v-model="basicTableData.showTableData" title="ShowTableData" />
        <HstText v-model="basicTableData.emptyText" title="EmptyText" />
        <HstNumber v-model="basicTableData.height" title="Height" />
        <HstRadio
          v-model="basicTableData.size"
          title="Size"
          :options="basicTableData.sizeOptions"
        />
        <HstRadio
          v-model="basicTableData.align"
          title="Align"
          :options="basicTableData.alignOptions"
        />
        <HstCheckbox v-model="basicTableData.stripe" title="Stripe" />
        <HstCheckbox v-model="basicTableData.border" title="Border" />
        <HstCheckbox v-model="basicTableData.fixed" title="Fixed" />
        <HstCheckbox v-model="basicTableData.sortable" title="Sortable" />
        <HstCheckbox v-model="basicTableData.fit" title="Fit" />
        <HstCheckbox v-model="basicTableData.showHeader" title="ShowHeader" />
        <HstCheckbox v-model="basicTableData.highlightCurrentRow" title="HighlightCurrentRow" />
        <HstCheckbox v-model="basicTableData.showOverflowTooltip" title="ShowOverflowTooltip" />
        <HstCheckbox v-model="basicTableData.flexible" title="Flexible" />
        <HstCheckbox v-model="basicTableData.scrollbarAlwaysOn" title="ScrollbarAlwaysOn" />
        <HstCheckbox v-model="basicTableData.showSummary" title="ShowSummary" />

        <HstCheckbox v-model="basicTableData.resizable" title="Resizable" />
      </template>
    </Variant>
  </Story>
</template>

<style scoped>
</style>

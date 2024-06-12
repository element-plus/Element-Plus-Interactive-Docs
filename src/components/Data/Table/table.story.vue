<script setup lang="ts">
import { onMounted, ref } from 'vue'
import sizeOptions from '@constants/sizeOptions'
import { alignOptions, tableLayoutOptions } from './constants'

/** Basic-Table */
const tableData = ref([])

/** generateData */
function generateData(): any {
  for (let i = 1; i <= 10; i++) {
    tableData.value.push({
      name: `Name ${i}`,
      age: Math.floor(Math.random() * 50) + 20,
      gender: i % 2 === 0 ? 'Male' : 'Female',
      country: `Country ${i}`,
      city: `City ${i}`,
      income: Math.floor(Math.random() * 10000) + 5000,
      email: `email${i}@example.com`,
      phone: `123456789${i}`,
      address: `Address ${i}`,
      registrationDate: '2022-01-01',
      date: '2022-01-01',
      status: i % 3 === 0 ? 'Active' : 'Inactive',
      family: [
        {
          name: 'Jerry',
          state: 'California',
          city: 'San Francisco',
          address: '3650 21st St, San Francisco',
          zip: 'CA 94114',
        },
      ],
    })
  }
}

onMounted(() => {
  generateData()
})

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
  tableLayoutOptions,
  tableLayout: 'fixed',
})

/** Basic-Table-Column */
const basicTableColumn = reactive([
  { label: 'Name', prop: 'name' },
  { label: 'Age', prop: 'age' },
  { label: 'Country', prop: 'country' },
  { label: 'City', prop: 'city' },
  { label: 'Income', prop: 'income' },
  { label: 'Email', prop: 'email' },
  { label: 'Phone', prop: 'phone' },
  { label: 'Address', prop: 'address' },
  { label: 'Date', prop: 'registrationDate' },
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

/** arraySpanMethod */
function arraySpanMethod(span: SpanMethodProps) {
  if (span.rowIndex % 2 === 0) {
    if (span.columnIndex === 0)
      return [1, 2]
    else if (span.columnIndex === 1)
      return [0, 0]
  }
}

/** basicTableSource */
const basicTableSource = computed(() => {
  return `
<script setup lang="ts">
import { onMounted, reactive, ref } from 'vue'
const tableData = ref([])

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

/** generateData */
function generateData(): any {
  for (let i = 1; i <= 10; i++) {
    tableData.value.push({
      name: \`Name \${i}\`,
      age: Math.floor(Math.random() * 50) + 20,
      gender: i % 2 === 0 ? 'Male' : 'Female',
      country: \`Country \${i}\`,
      city: \`City \${i}\`,
      income: Math.floor(Math.random() * 10000) + 5000,
      email: \`email\${i}@example.com\`,
      phone: \`123456789\${i}\`,
      address: \`Address \${i}\`,
      registrationDate: \'2022-01-01\',
      status: i % 3 === 0 ? 'Active' : 'Inactive',
    })
  }
}

onMounted(() => {
  generateData()
})

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

/** customTableSource */
const customTableSource = computed(() => {
  return `
<script setup lang="ts">
import { onMounted, reactive, ref } from 'vue'
const tableData = ref([])

/** generateData */
function generateData(): any {
  for (let i = 1; i <= 10; i++) {
    tableData.value.push({
      name: \`Name \${i}\`,
      date: '2022-01-01',
      status: i % 3 === 0 ? 'Active' : 'Inactive',
      family: [
        {
          name: 'Jerry',
          state: 'California',
          city: 'San Francisco',
          address: '3650 21st St, San Francisco',
          zip: 'CA 94114',
        },
      ],
    })
  }
}

onMounted(() => {
  generateData()
})

/** arraySpanMethod */
function arraySpanMethod(span: SpanMethodProps) {
  if (span.rowIndex % 2 === 0) {
    if (span.columnIndex === 0)
      return [1, 2]
    else if (span.columnIndex === 1)
      return [0, 0]
  }
}

<\/script>

<template>
  <el-table
        :data="tableData"
        style="width: 100%"
        :span-method="arraySpanMethod"
      >
        <el-table-column type="index" />
        <el-table-column type="expand">
          <template #default="props">
            <div m="4">
              <p m="t-0 b-2">
                Status: {{ props.row.status }}
              </p>
              <p m="t-0 b-2">
                City: {{ props.row.city }}
              </p>
              <p m="t-0 b-2">
                Address: {{ props.row.address }}
              </p>
              <h3>Family</h3>
              <el-table :data="props.row.family" :border="childBorder">
                <el-table-column label="Name" prop="name" />
                <el-table-column label="State" prop="state" />
                <el-table-column label="City" prop="city" />
                <el-table-column label="Address" prop="address" />
                <el-table-column label="Zip" prop="zip" />
              </el-table>
            </div>
          </template>
        </el-table-column>
        <el-table-column label="Date" width="180">
          <template #default="scope">
            <div style="display: flex; align-items: center">
              <el-icon><timer /></el-icon>
              <span style="margin-left: 10px">{{ scope.row.date }}</span>
            </div>
          </template>
        </el-table-column>
        <el-table-column label="Name" width="180">
          <template #default="scope">
            <el-popover effect="light" trigger="hover" placement="top" width="auto">
              <template #default>
                <div>name: {{ scope.row.name }}</div>
                <div>address: {{ scope.row.address }}</div>
              </template>
              <template #reference>
                <el-tag>{{ scope.row.name }}</el-tag>
              </template>
            </el-popover>
          </template>
        </el-table-column>
        <el-table-column label="Operations">
          <template #header>
            <el-input v-model="search" size="small" placeholder="Type to search" />
          </template>
          <template #default="scope">
            <el-button size="small" @click="handleEdit(scope.$index, scope.row)">
              Edit
            </el-button>
            <el-button
              size="small"
              type="danger"
              @click="handleDelete(scope.$index, scope.row)"
            >
              Delete
            </el-button>
          </template>
        </el-table-column>
      </el-table>
</template>
`
})
</script>

<template>
  <Story
    title="Data/Table"
    icon="material-symbols-light:data-table-outline"
    :layout="{
      type: 'single',
      iframe: false,
    }"
  >
    <Variant
      title="Basic Table"
      :source="basicTableSource"
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
        :table-layout="basicTableData.tableLayout"
      >
        <el-table-column
          v-for="(item, index) in basicTableColumn"
          :key="index"
          min-width="120px"
          :label="item.label"
          :prop="item.prop"
          :fixed="item.label === 'Name' || item.label === 'Status' ? basicTableData.fixed : false"
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
        <HstButtonGroup
          v-model="basicTableData.tableLayout"
          title="Table Layout"
          :options="basicTableData.tableLayoutOptions"
        />
        <HstButtonGroup
          v-model="basicTableData.size"
          title="Size"
          :options="basicTableData.sizeOptions"
        />
        <HstButtonGroup
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

    <Variant
      title="Custom Table"
      :source="customTableSource"
    >
      <el-table
        :data="tableData"
        style="width: 100%"
        :span-method="arraySpanMethod"
      >
        <el-table-column type="index" />
        <el-table-column type="expand">
          <template #default="props">
            <div m="4">
              <p m="t-0 b-2">
                Status: {{ props.row.status }}
              </p>
              <p m="t-0 b-2">
                City: {{ props.row.city }}
              </p>
              <p m="t-0 b-2">
                Address: {{ props.row.address }}
              </p>
              <h3>Family</h3>
              <el-table :data="props.row.family" :border="childBorder">
                <el-table-column label="Name" prop="name" />
                <el-table-column label="State" prop="state" />
                <el-table-column label="City" prop="city" />
                <el-table-column label="Address" prop="address" />
                <el-table-column label="Zip" prop="zip" />
              </el-table>
            </div>
          </template>
        </el-table-column>
        <el-table-column label="Date" width="180">
          <template #default="scope">
            <div style="display: flex; align-items: center">
              <el-icon><timer /></el-icon>
              <span style="margin-left: 10px">{{ scope.row.date }}</span>
            </div>
          </template>
        </el-table-column>
        <el-table-column label="Name" width="180">
          <template #default="scope">
            <el-popover effect="light" trigger="hover" placement="top" width="auto">
              <template #default>
                <div>name: {{ scope.row.name }}</div>
                <div>address: {{ scope.row.address }}</div>
              </template>
              <template #reference>
                <el-tag>{{ scope.row.name }}</el-tag>
              </template>
            </el-popover>
          </template>
        </el-table-column>
        <el-table-column label="Operations">
          <template #header>
            <el-input v-model="search" size="small" placeholder="Type to search" />
          </template>
          <template #default="scope">
            <el-button size="small" @click="handleEdit(scope.$index, scope.row)">
              Edit
            </el-button>
            <el-button
              size="small"
              type="danger"
              @click="handleDelete(scope.$index, scope.row)"
            >
              Delete
            </el-button>
          </template>
        </el-table-column>
      </el-table>
      <template #controls />
    </Variant>
  </Story>
</template>

<style scoped>
</style>

<template>
  <Select
    :placeholder="placeholder"
    clearable
    :multiple="multiple"
    :value.sync="value"
    @on-change="change"
  >
    <template v-for="item1 in items">
      <Option
        :key="item1.id"
        :value="item1.id"
        :label="item1.name"
        :disabled="!selectParent"
      >
        {{ item1.name }}
      </Option>
      <Option
        v-for="item2 in item1.children"
        :key="item2.id"
        :value="item2.id"
        :label="item2.name"
      >
        &nbsp;&nbsp;&nbsp;&nbsp;{{ item2.name }}
      </Option>
    </template>
  </Select>
</template>

<script src="./script.js"></script>

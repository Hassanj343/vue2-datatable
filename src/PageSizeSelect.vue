<template>
  <label name="PageSizeSelect">
    <select class="block appearance-none w-full py-1 px-2 mb-1 text-base leading-normal bg-white text-gray-800 border border-gray-200 rounded input-sm -page-size-select" v-model="query.limit"
      @change="query.offset = 0 /* reset to the first page */">
      <option v-for="i in pageSizeOptions" :value="i">{{ i }}</option>
    </select>
    {{ $i18nForDatatable('items / page') }}
  </label>
</template>
<script>
export default {
  name: 'PageSizeSelect',
  props: {
    query: { type: Object, required: true },
    pageSizeOptions: { type: Array, required: true }
  }
}
</script>
<style>
.-page-size-select {
  display: inline-block;
  width: 65px;
}
</style>

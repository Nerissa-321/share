<template>
  <div class="">
    <a-table bordered :data-source="dataSource" :columns="columns">
      <template #bodyCell="{ column, text, record }">
        <template v-if="column.dataIndex === 'wechat'">
          <a-image width="100%" :src="record.wechat" />
        </template>
        <template v-else-if="column.dataIndex === 'operation'">
          <a-switch v-model:checked="record.checked" @change="handleChange" />
        </template>
        <template v-else>
          {{ text || " " }}
        </template>
      </template>
    </a-table>
  </div>
</template>

<script setup>
import { ref } from "vue";
const columns = [
  {
    title: "日期",
    dataIndex: "date",
    width: "15%",
  },
  {
    title: "Name",
    dataIndex: "name",
  },
  {
    title: "Email",
    dataIndex: "email",
  },
  {
    title: "Subject",
    dataIndex: "subject",
  },
  {
    title: "Message",
    dataIndex: "message",
  },
  {
    title: "Wechat",
    dataIndex: "wechat",
  },
  {
    title: "operation",
    dataIndex: "operation",
  },
];
const dataSource = ref([
  {
    requestId: "0",
    date: "Edward King 0",
    name: 32,
    email: "edwardking@yahoo.com",
    subject: "London, Park Lane no. 0",
    message: "London, Park Lane no. 0",
    wechat:
      "https://zos.alipayobjects.com/rmsportal/jkjgkEfvpUPVyRjUImniVslZfWPnJuuZ.png",
    checked: true,
  },
  {
    requestId: "0",
    date: "Edward King 0",
    name: 32,
    email: "edwardking@yahoo.com",
    subject: "London, Park Lane no. 0",
    message: "London, Park Lane no. 0",
    wechat:
      "https://zos.alipayobjects.com/rmsportal/jkjgkEfvpUPVyRjUImniVslZfWPnJuuZ.png",
    checked: true,
  },
  {
    requestId: "0",
    date: "Edward King 0",
    name: 32,
    email: "edwardking@yahoo.com",
    subject: "London, Park Lane no. 0",
    message: "London, Park Lane no. 0",
    wechat:
      "https://zos.alipayobjects.com/rmsportal/jkjgkEfvpUPVyRjUImniVslZfWPnJuuZ.png",
    checked: true,
  },
]);
const handleChange = (checked, record) => {
  console.log(checked, record);
};
</script>

<style scoped lang="scss">
.editable-cell {
  position: relative;
  .editable-cell-input-wrapper,
  .editable-cell-text-wrapper {
    padding-right: 24px;
  }

  .editable-cell-text-wrapper {
    padding: 5px 24px 5px 5px;
  }

  .editable-cell-icon,
  .editable-cell-icon-check {
    position: absolute;
    right: 0;
    width: 20px;
    cursor: pointer;
  }

  .editable-cell-icon {
    margin-top: 4px;
    display: none;
  }

  .editable-cell-icon-check {
    line-height: 28px;
  }

  .editable-cell-icon:hover,
  .editable-cell-icon-check:hover {
    color: #108ee9;
  }

  .editable-add-btn {
    margin-bottom: 8px;
  }
}
.editable-cell:hover .editable-cell-icon {
  display: inline-block;
}
</style>

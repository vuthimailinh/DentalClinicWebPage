<script setup>
import { ref } from "vue";

const itemMenu = ref([
    {
        title: 'Quản Lý Lịch Khám',
    },
    {
        title: 'Quản Lý Thông Tin',
        item: [
          { 
            subItem: 'Thông tin bác sĩ',
          }, 
          {
            subItem: 'Thông tin dịch vụ'
          },
          {
            subItem: 'Combo ưu đãi'
          }
      ]
    },
    {
        title: 'Quản Lý Customer'
    }, 
    {
        title: 'Quản Lý Staff'
    }, 
    {
        title: 'Quản Lý Giao Dịch'
    },
    {
        title: 'Quản Lý Dữ Liệu Đánh Giá'
    },
    {
        title: 'Thống Kê Doanh Thu'
    },
    {
        title: 'Cài Đặt',
        item: [
          { 
            subItem: 'Thông tin cá nhân',
          }, 
          {
            subItem: 'Đổi mật khẩu'
          }
      ]
    }
]);
</script>

<template>
<div class="flex flex-column gap-5 border-right-2 border-transparent w-23rem">
    <div class="flex justify-content-center border-bottom-2 border-blue-500 py-4">
      <span class="text-2xl p-1 text-blue-400 font-bold">PHÒNG KHÁM</span>
    </div>

    <div class="flex flex-column gap-5 pl-3">
      <div v-for="( menu,index ) in itemMenu" :key="index" class="flex flex-column gap-3">
        <!-- item menu -->
        <div class="flex justify-content-between mr-3 align-items-end">
            <div class="flex gap-3 align-items-center font-semibold">
                <i class="pi pi-home"></i>
                <span class="cursor-pointer">{{ menu.title }}</span>
            </div>
            <i class="pi pi-angle-right"></i>
        </div>
        <!-- Sub item menu -->
        <div v-for="( subMenu,index ) in menu.item" :key="index" class="flex flex-column gap-3 ml-5">
            <span class="cursor-pointer w-fit-content">{{ subMenu.subItem }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.border-custom{
  border: 1px solid;
  border-color: linear-gradient(rgb(100, 230, 226), #9198e5);
}
</style>
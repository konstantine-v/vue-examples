<template>
  <Disclosure as="nav" class="bg-gray-800" v-slot="{ open }">
    <div class="px-2 mx-auto max-w-7xl sm:px-6 lg:px-8">
      <div class="flex relative justify-between items-center h-16">

        <!-- Mobile menu button-->
        <div class="flex absolute inset-y-0 left-0 items-center sm:hidden">
          <DisclosureButton class="inline-flex relative justify-center items-center p-2 text-gray-400 rounded-md hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
            <span class="absolute -inset-0.5" />
            <span class="sr-only">Open main menu</span>
            <Bars3Icon v-if="!open" class="block w-6 h-6" aria-hidden="true" />
            <XMarkIcon v-else class="block w-6 h-6" aria-hidden="true" />
          </DisclosureButton>
        </div>

        <!-- Nav Items -->
        <!-- Left Side -->
        <!-- Company Logo -->
        <div class="flex flex-1 justify-center items-center sm:items-stretch sm:justify-start">
          <!-- List of menu items -->
          <div class="hidden sm:ml-6 sm:block">
            <div class="flex space-x-4">
              <a v-for="item in navigation" :key="item.name" :href="item.href" :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'rounded-md px-3 py-2 text-sm font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</a>
            </div>
          </div>
        </div>
        
        <!-- Right Side -->
        <!-- Notifications -->
        <div class="flex absolute inset-y-0 right-0 items-center pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0">
          <!-- <button type="button" class="relative p-1 text-gray-400 bg-gray-800 rounded-full hover:text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
            <span class="absolute -inset-1.5" />
            <span class="sr-only">View notifications</span>
            <BellIcon class="w-6 h-6" aria-hidden="true" />
          </button> -->

          <!-- Profile Image/Button -->
          <Menu as="div" class="relative ml-3">
            <div>
              <MenuButton class="relative p-1 text-gray-400 bg-gray-800 rounded-full hover:text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <span class="absolute -inset-1.5" />
                <span class="sr-only">View notifications</span>
                <BellIcon class="w-6 h-6" aria-hidden="true" />
              </MenuButton>

              <transition enter-active-class="transition duration-100 ease-out" enter-from-class="opacity-0 transform scale-95" enter-to-class="opacity-100 transform scale-100" leave-active-class="transition duration-75 ease-in" leave-from-class="opacity-100 transform scale-100" leave-to-class="opacity-0 transform scale-95">
              <MenuItems class="absolute right-0 z-10 py-1 mt-2 w-48 bg-white rounded-md ring-1 ring-black ring-opacity-5 shadow-lg origin-top-right focus:outline-none">
                <MenuItem v-slot="{ active }" v-for="item in notifications" :key="item.data">
                  <a href="#" :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']">{{ item.data }}</a>
                </MenuItem>
              </MenuItems>
            </transition>
            </div>

            <!-- End of Menu -->
          </Menu>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <DisclosurePanel class="sm:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href" :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'block rounded-md px-3 py-2 text-base font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
      </div>
    </DisclosurePanel>
  </Disclosure>

</template>

<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel, Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'

const navigation = [
  { name: 'Home', href: '#', current: true },
  { name: 'Weather', href: '#/404', current: false },
  { name: 'RSS', href: '#/404', current: false },
  { name: 'Calendar', href: '#/404', current: false },
]

const notifications = [
  { data: 'Update v0.1.1 - Something here...' },
  { data: 'Update v0.1.0 - init...' },
]
</script>
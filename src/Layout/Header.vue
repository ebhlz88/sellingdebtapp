<template>
    <div id="header" class="czarna-container pt-4 pb-3">
        <div class="logo w-36"></div>
    <div class="links hidden sm:flex ml-auto lg:ml-0">
      <a
        class="nav-link lg:text-base md:text-sm sm:text-sm text-xs">
        Giełda długów
        <div class="border"></div>
      </a>
      <a
        class="nav-link lg:text-base md:text-sm sm:text-sm text-xs">
        Alerty
        <div class="border"></div>
      </a>
      <a
        class="nav-link lg:text-base md:text-sm sm:text-sm text-xs">
        Cennik
        <div class="border"></div>
      </a>
      <a>
        Baza wiedzy
        <div class="border"></div>
      </a>
      <a class="nav-link lg:text-base md:text-sm sm:text-sm text-xs">
        Kontakt
        <div class="border"></div>
      </a>
    </div>
    <div class="actions hidden lg:flex ">
      <div class="flex-column relative">
      <button
        class="bg-white hover:z-50 text-gray-400 font-semibold py-3 px-4 border border-lightgray-500 rounded-lg text-custom-gray hover:ease-in mx-2.5 action-btn lg:text-base md:text-sm sm:text-sm text-xs flex items-center profile-btn"
      >
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 13.84 17.87" class="mr-2 h-6 w-4">
          <g id="Iconly_Light_Profile" data-name="Iconly/Light/Profile" transform="translate(0.75 0.714)">
            <g id="Profile">
              <path id="Stroke_1" data-name="Stroke 1" d="M6.17,0C2.842,0,0,.521,0,2.609S2.824,5.236,6.17,5.236c3.328,0,6.17-.522,6.17-2.609S9.517,0,6.17,0Z" transform="translate(0 11.17)" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5"/>
              <path id="Stroke_3" data-name="Stroke 3" d="M3.955,8.193A4.028,4.028,0,0,0,7.91,4.1,4.027,4.027,0,0,0,3.955,0,4.027,4.027,0,0,0,0,4.1a4.015,4.015,0,0,0,3.927,4.1Z" transform="translate(2.215)" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.429"/>
            </g>
          </g>
        </svg>
        Moje konto
      </button>
      <button
        class="bg-white text-center absolute hover:z-50 text-gray-400 font-semibold py-3 px-7 border border-lightgray-500 rounded text-custom-gray hover:ease-in mx-2.5 action-btn lg:text-base md:text-sm sm:text-sm text-xs flex items-center profile-btn"
      >
       Moje długi
      </button>
      <button
        class="bg-white absolute hover:z-50 text-gray-400 font-semibold py-3 px-10 border border-lightgray-500 rounded text-custom-gray hover:ease-in mx-2.5 action-btn lg:text-base md:text-sm sm:text-sm text-xs flex items-center profile-btn">
        Wyloguj
      </button>
      </div>
      <button
        class="text-white font-semibold py-3 px-4 border rounded-lg hover:ease-in mx-2.5 action-btn lg:text-base md:text-sm sm:text-sm text-xs flex items-center czarna-btn-red">
        Sprzedaj dług
      </button>
    </div>
     <Menu as="div" class="relative inline-block text-left flex lg:hidden z-200">
      <div>
        <MenuButton
          class="border border-red-500 py-2 px-3 rounded-lg bg-white hover:bg-red-500 text-red-500 hover:text-white transition-all"
        >
          <font-awesome-icon :icon="{prefix: 'fas', iconName: 'bars'}"/>
        </MenuButton>
      </div>

      <transition
        enter-active-class="transition duration-100 ease-out"
        enter-from-class="transform scale-95 opacity-0"
        enter-to-class="transform scale-100 opacity-100"
        leave-active-class="transition duration-75 ease-in"
        leave-from-class="transform scale-100 opacity-100"
        leave-to-class="transform scale-95 opacity-0"
      >
        <MenuItems
          class="absolute right-0 w-56 mt-2 origin-top-right bg-white divide-y divide-gray-100 rounded-md shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none"
        >
          <div class="px-1 py-1 block sm:hidden">
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-violet-500 text-white' : 'text-gray-900',
                  'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                ]"
                @click="navigate('/')"
              >
                Giełda długów
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-violet-500 text-white' : 'text-gray-900',
                  'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                ]"
                @click="navigate('/add-alert')"
              >
                Alerty
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-violet-500 text-white' : 'text-gray-900',
                  'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                ]"
                @click="navigate('/prices')"
              >
                Cennik
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-violet-500 text-white' : 'text-gray-900',
                  'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                ]"
                @click="navigate('/info')"
              >
                Baza wiedzy
              </button>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <button
                :class="[
                  active ? 'bg-violet-500 text-white' : 'text-gray-900',
                  'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                ]"
              >
                Kontakt
              </button>
            </MenuItem>
          </div>
          <div class="dropdown px-2 py-2">
            <div class="flex-col">
            <button
              class="py-1 px-2 border border-gray-200 text-gray-600 w-full rounded-lg mb-1"
            >
              <font-awesome-icon :icon="{ prefix: 'far', iconName: 'user' }" class="mr-2" />Moje konto
            </button>
            </div>
            <button
              class="px-2 py-1 bg-red-600 text-white w-full rounded-lg"
            >
              Sprzedaj dług
            </button>
          </div>
        </MenuItems>
      </transition>
    </Menu>
    </div>
</template>

<script>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
export default {
    name: "Header",
    components: {
        Menu,
        MenuButton,
        MenuItems,
        MenuItem,
    },
};
</script>

<style scoped>
div#header {
  box-shadow: 0px 8px 36px #525f7a14;
  background: #ffffff 0% 0% no-repeat padding-box;

  display: flex;
  justify-content: space-between;
  align-items: center;

  z-index: 1001;

  position: fixed;
  top: 0;
  left: 0;
  right: 0;
}

div.logo {
  height: 3rem;
  background: #eff3f7 0% 0% no-repeat padding-box;
}

div.links a.nav-link {
  letter-spacing: 0px;
  color: #14161f;
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0px 10px;
  position: relative;
  font-weight: 300;
}

div.links a.nav-link:hover {
  cursor: pointer;
}

div.links a.nav-link .border {
  position: absolute;
  top: 32.5px;
  transform: translate(-50%, -50%);
  left: 50%;
  height: 0px;
  width: 25px;
  border: 1px solid transparent;
}

div.links .selected {
  font-weight: bold !important;
}

div.links .selected .border {
  border: 1px solid #e7334b !important;
}

button.action-btn {
  display: flex;
  line-height: 1rem;
  transition: all 0.2s;
}

button.profile-btn:hover {
  border-color: #CC2D42;
  color: #CC2D42;
}

button.profile-btn:hover svg {
  fill: #CC2D42;
}

.z-200 {
  z-index: 200;
}
#header .actions .absolute{
  top: 16px;
  width: 143px;
  height: 50px;
}
#header .actions :nth-child(2) {
  top: 46px;
}
#header .actions :nth-child(3) {
  top: 90px;
}
</style>

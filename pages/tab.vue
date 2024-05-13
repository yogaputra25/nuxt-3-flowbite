<script setup>
import { onMounted } from "vue";
import { Tabs } from "flowbite";
onMounted(() => {
  const tabsElement = document.getElementById("tabs-example");

  // create an array of objects with the id, trigger element (eg. button), and the content element
  const tabElements = [
    {
      id: "profile",
      triggerEl: document.querySelector("#profile-tab-example"),
      targetEl: document.querySelector("#profile-example"),
    },
    {
      id: "dashboard",
      triggerEl: document.querySelector("#dashboard-tab-example"),
      targetEl: document.querySelector("#dashboard-example"),
    },
    {
      id: "settings",
      triggerEl: document.querySelector("#settings-tab-example"),
      targetEl: document.querySelector("#settings-example"),
    },
    {
      id: "contacts",
      triggerEl: document.querySelector("#contacts-tab-example"),
      targetEl: document.querySelector("#contacts-example"),
    },
  ];
  // options with default values
  const options = {
    defaultTabId: "settings",
    activeClasses:
      "text-blue-600 hover:text-blue-600 dark:text-blue-500 dark:hover:text-blue-400 border-blue-600 dark:border-blue-500",
    inactiveClasses:
      "text-gray-500 hover:text-gray-600 dark:text-gray-400 border-gray-100 hover:border-gray-300 dark:border-gray-700 dark:hover:text-gray-300",
    onShow: () => {
      console.log("tab is shown");
    },
  };
  if (document.querySelector("#profile-tab-example")) {
    /*
     * tabElements: array of tab objects
     * options: optional
     */
    const tabs = new Tabs(tabsElement, tabElements, options);
    // open tab item based on id
    tabs.show("contacts");
  }
});
</script>

<template>
  <div class="max-w-2xl p-4 mx-auto">
    <div class="mb-4 border-b border-gray-200 dark:border-gray-700">
      <ul
        class="flex flex-wrap -mb-px text-sm font-medium text-center text-gray-500 dark:text-gray-400"
        id="tabs-example"
        role="tablist"
      >
        <li class="mr-2" role="presentation">
          <button
            class="inline-block p-4 border-b-2 border-transparent rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300"
            id="profile-tab-example"
            type="button"
            role="tab"
            aria-controls="profile-example"
            aria-selected="false"
          >
            Profile
          </button>
        </li>
        <li class="mr-2" role="presentation">
          <button
            class="inline-block p-4 border-b-2 border-transparent rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300"
            id="dashboard-tab-example"
            type="button"
            role="tab"
            aria-controls="dashboard-example"
            aria-selected="false"
          >
            Dashboard
          </button>
        </li>
        <li class="mr-2" role="presentation">
          <button
            class="inline-block p-4 border-b-2 border-transparent rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300"
            id="settings-tab-example"
            type="button"
            role="tab"
            aria-controls="settings-example"
            aria-selected="false"
          >
            Settings
          </button>
        </li>
        <li role="presentation">
          <button
            class="inline-block p-4 border-b-2 border-transparent rounded-t-lg hover:text-gray-600 hover:border-gray-300 dark:hover:text-gray-300"
            id="contacts-tab-example"
            type="button"
            role="tab"
            aria-controls="contacts-example"
            aria-selected="false"
          >
            Contacts
          </button>
        </li>
      </ul>
    </div>
    <div id="tabContentExample">
      <div
        class="hidden p-4 rounded-lg bg-gray-50 dark:bg-gray-800"
        id="profile-example"
        role="tabpanel"
        aria-labelledby="profile-tab-example"
      >
        <p class="text-sm text-gray-500 dark:text-gray-400">
          This is some placeholder content the
          <strong class="font-medium text-gray-800 dark:text-white"
            >Profile tab's associated content</strong
          >. Clicking another tab will toggle the visibility of this one for the
          next. The tab JavaScript swaps classes to control the content
          visibility and styling.
        </p>
      </div>
      <div
        class="hidden p-4 rounded-lg bg-gray-50 dark:bg-gray-800"
        id="dashboard-example"
        role="tabpanel"
        aria-labelledby="dashboard-tab-example"
      >
        <p class="text-sm text-gray-500 dark:text-gray-400">
          This is some placeholder content the
          <strong class="font-medium text-gray-800 dark:text-white"
            >Dashboard tab's associated content</strong
          >. Clicking another tab will toggle the visibility of this one for the
          next. The tab JavaScript swaps classes to control the content
          visibility and styling.
        </p>
      </div>
      <div
        class="hidden p-4 rounded-lg bg-gray-50 dark:bg-gray-800"
        id="settings-example"
        role="tabpanel"
        aria-labelledby="settings-tab-example"
      >
        <p class="text-sm text-gray-500 dark:text-gray-400">
          This is some placeholder content the
          <strong class="font-medium text-gray-800 dark:text-white"
            >Settings tab's associated content</strong
          >. Clicking another tab will toggle the visibility of this one for the
          next. The tab JavaScript swaps classes to control the content
          visibility and styling.
        </p>
      </div>
      <div
        class="hidden p-4 rounded-lg bg-gray-50 dark:bg-gray-800"
        id="contacts-example"
        role="tabpanel"
        aria-labelledby="contacts-tab-example"
      >
        <p class="text-sm text-gray-500 dark:text-gray-400">
          This is some placeholder content the
          <strong class="font-medium text-gray-800 dark:text-white"
            >Contacts tab's associated content</strong
          >. Clicking another tab will toggle the visibility of this one for the
          next. The tab JavaScript swaps classes to control the content
          visibility and styling.
        </p>
      </div>
    </div>

    <div
      class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl"
    >
      <div class="md:flex">
        <div class="md:shrink-0">
          <img
            class="h-48 w-full object-cover md:h-full md:w-48"
            src="/1.webp"
            alt="Modern building architecture"
          />
        </div>
        <div class="p-8">
          <div
            class="uppercase tracking-wide text-sm text-indigo-500 font-semibold"
          >
            Company retreats
          </div>
          <a
            href="#"
            class="block mt-1 text-lg leading-tight font-medium text-black hover:underline"
            >Incredible accommodation for your team</a
          >
          <p class="mt-2 text-slate-500">
            Looking to take your team away on a retreat to enjoy awesome food
            and take in some sunshine? We have a list of places to do just that.
          </p>
        </div>
      </div>
    </div>

    <div>
      <div class="flex space-x-2 items-center text-base">
        <h4 class="font-semibold text-slate-900">Contributors</h4>
        <span
          class="rounded-full bg-slate-100 px-2 py-1 text-xs font-semibold text-slate-700"
          >204</span
        >
        <span
          class="rounded-full bg-slate-100 px-2 py-1 text-xs font-semibold text-slate-700"
          >204</span
        >
      </div>
      <div class="mt-3 flex -space-x-2 overflow-hidden">
        <img
          class="inline-block h-12 w-12 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
          alt=""
        />
        <img
          class="inline-block h-12 w-12 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
          alt=""
        />
        <img
          class="inline-block h-12 w-12 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2.25&w=256&h=256&q=80"
          alt=""
        />
        <img
          class="inline-block h-12 w-12 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
          alt=""
        />
        <img
          class="inline-block h-12 w-12 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
          alt=""
        />
      </div>
      <div class="mt-3 text-sm font-medium">
        <a href="#" class="text-blue-500">+ 198 others</a>
      </div>
    </div>
  </div>
  <iframe
    class="w-full aspect-video hover:aspect-square"
    src="http://localhost:3000"
  ></iframe>
</template>

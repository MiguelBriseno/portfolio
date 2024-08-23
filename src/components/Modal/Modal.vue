<template>
  <TransitionRoot as="template" :show="open" @close="handleClose">
    <Dialog class="relative z-10" @close="handleClose">
      <TransitionChild
        as="template"
        enter="ease-out duration-300"
        enter-from="opacity-0"
        enter-to="opacity-100"
        leave="ease-in duration-200"
        leave-from="opacity-100"
        leave-to="opacity-0"
      >
        <div
          class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"
        />
      </TransitionChild>

      <div class="fixed inset-0 z-10 w-screen overflow-y-auto">
        <div
          class="flex min-h-full items-end justify-center p-4 text-center sm:items-center sm:p-0"
        >
          <TransitionChild
            as="template"
            enter="ease-out duration-300"
            enter-from="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
            enter-to="opacity-100 translate-y-0 sm:scale-100"
            leave="ease-in duration-200"
            leave-from="opacity-100 translate-y-0 sm:scale-100"
            leave-to="opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
          >
            <DialogPanel
              class="relative transform overflow-hidden rounded-lg bg-gray-800 px-4 pb-4 pt-5 text-left text-white shadow-xl transition-all sm:my-8 sm:max-w-3xl sm:p-6"
            >
              <div>
                <div class="relative w-full">
                  <DialogTitle
                    as="h2"
                    class="text-2xl font-semibold text-white"
                    >{{ post.title }}</DialogTitle
                  >
                </div>
                <div class="relative w-full py-5">
                  <div class="flex border-t border-gray-900/5">
                    <div class="relative flex items-center gap-x-4">
                      <img
                        :src="post.author.imageUrl"
                        alt=""
                        class="h-11 w-11 rounded-full bg-gray-50"
                      />
                      <div class="text-sm leading-6">
                        <p class="font-semibold text-gray-400">
                          <a :href="post.author.href">
                            <span class="absolute inset-0" />
                            {{ post.author.name }}
                          </a>
                        </p>
                        <p class="text-gray-200">{{ post.author.role }}</p>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="relative w-full p-5">
                  <img
                    :src="post.imageUrl"
                    alt=""
                    class="aspect-[16/9] w-full rounded-2xl bg-gray-100 object-cover sm:aspect-[2/1] lg:aspect-[4/2]"
                  />
                  <div
                    class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10"
                  />
                </div>
                <div class="mt-3 text-center sm:mt-5 p-5">
                  <div class="mt-2">
                    <p class="text-sm leading-7 text-gray-300 text-justify">
                      {{ post.description }}
                    </p>
                    <p class="font-semibold text-gray-400">{{ post.date }}</p>
                  </div>
                </div>
              </div>
              <div class="mt-5 sm:mt-6">
                <button
                  type="button"
                  class="inline-flex w-full justify-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                  @click="handleClose"
                >
                  Close
                </button>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>
  
<script setup>
import { defineProps, defineEmits } from "vue";
import { Dialog, TransitionRoot, TransitionChild } from "@headlessui/vue";

const props = defineProps({
  open: Boolean,
  post: Object,
});

const emit = defineEmits(["close"]);

const handleClose = () => {
  emit("close");
};
</script>  
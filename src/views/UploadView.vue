<template>
  <div>
    <div class="mb-8">
      <app-uploader/>
    </div>

    <div>
      <h2 class="font-medium pb-3 border-b-2 border-gray-100 text-gray-800">Your files</h2>

      <template v-if="files.length">
        <app-file v-for="file in files" :key="file.uuid" :file="file" />
      </template>
      <p v-else class="mt-3 text-sm text-gray-800">There are no files here right now</p>
    </div>
  </div>
</template>

<script>
import {mapActions, mapGetters} from "vuex"
import AppFile from "@/components/AppFile"
import AppUploader from "@/components/AppUploader";

export default {
  components: {
    AppUploader,
    AppFile
  },
  computed: {
    ...mapGetters({
      files: 'files/files'
    })
  },
  methods: {
    ...mapActions({
      getFiles: 'files/getFiles'
    })
  },

  mounted() {
    this.getFiles()
  }
}
</script>

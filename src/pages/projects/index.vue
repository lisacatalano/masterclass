<script setup lang="ts">
import type { Projects } from '@/utils/supaQueries';
import { projectsQuery } from '@/utils/supaQueries';
import { columns } from '@/utils/tableColumns/projectColumns';

usePageStore().pageData.title = 'Projects';

const projects = ref<Projects | null>(null);
const getProjects = async () => {
  const { data, error } = await projectsQuery
  if (error) console.log(error);
  projects.value = data;
}

await getProjects();

</script>
<template>
  <div>
    <DataTable v-if="projects" :columns="columns" :data="projects" />
  </div>
</template>

<style scoped></style>

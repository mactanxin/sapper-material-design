
<svelte:head>
	<title>Jobs</title>
</svelte:head>

<script context="module">
  export async function preload (page, session) {
    console.log(page, session)
    const res = await this.fetch('/data.json');
    const todos = await res.json();
    return { todos }
  }
</script>

<script>
  import {onMount} from 'svelte';
  import { List, ListItem, Icon } from 'svelte-materialify/src';
  import Button from 'svelte-materialify/src/components/Button';
  import { goto } from '@sapper/app';
  export let todos;
  onMount()

  async function goToCreate (e) {
    await goto('jobs/create');
  }
</script>

<style></style>

<h1>Recent Todos</h1>

<h2>
  {#each todos as todo}
    <List>
      <ListItem>{ todo.todo }</ListItem>
    </List>
  {/each}
</h2>

<Button  class="primary-color" on:click={ () => goto('jobs/create') }>Post a new job</Button>
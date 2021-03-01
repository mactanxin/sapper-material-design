
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
  export let todos;
  onMount(() => {
    console.log('todos: ', todos);
  })
  console.log('jobs');
</script>

<style></style>

<h1>Recent Jobs</h1>

<h2>
  {#each todos as todo}
    <ul>
      <li> { todo.todo }</li>
    </ul>
  {/each}
</h2>

<a href="jobs/create">Post a new job</a>
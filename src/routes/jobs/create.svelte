<script>
  let title;
  let salary;
  let details;
  const handleSubmit = () => {
    console.log(title, salary, details)
  }
</script>

<style>
  h2 {
    text-align: center;
  }

  form {
    max-width: 400px;
    text-align: center;
  }
  input, textarea {
    display: block;
    width: 100%;
    padding: 10px;
    margin: 10px auto;
    border-radius: 8px;
  } 
</style>
<h2>Add a new Job</h2>

<form on:submit|preventDefault="{handleSubmit}">
  <input type="text" placeholder="job title" bind:value={title} required>
  <input type="number" placeholder="salary" bind:value={salary} required>
  <textarea 
    name="details" id="" 
    placeholder="job details"  bind:value={details} required></textarea>
  <button class="btn">Post Job</button>
</form>
<script context="module">
  export async function load() {
    const res = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await res.json();
    console.log(users);
    return {
      props: {
        users,
      },
    };
  }
</script>

<script>
  export let users;
</script>

<div class="guides">
  <ul>
    {#each users as user}
      <li>
        <a href={`/users/${user.id}`}>{user.name}</a>
      </li>
    {/each}
  </ul>
</div>

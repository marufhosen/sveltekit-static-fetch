<script context="module">
  export async function load({ params }) {
    const id = params.id;
    const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
    const user = await res.json();

    return {
      props: {
        user,
      },
    };
  }
</script>

<script>
  export let user;
</script>

<div class="guide">
  <h2>{user.name}</h2>
  <p>{user.email}</p>
</div>

<script>
  let selectedCategory = "";

  const categories = [
    {
      name: "Onderzoeken en begrijpen",
      video: "https://www.youtube.com/embed/KaX4moO99mA?si=-Ga2yVRDq6corNkW",
      content: "Informatie over onderzoeken en begrijpen.",
    },
    {
      name: "Organiseren en plannen",
      video: "https://www.youtube.com/embed/hMSZTRgLT-o?si=Rgq8e0O4NJSclR8L",
      content: "Informatie over organiseren en plannen.",
    },
  ];
</script>

<main>
  <!-- Filtersectie -->
  <section>
    <ul>
      {#each categories as { name }}
        <li>
          <a
            href="javascript:void(0)"
            on:click={() => (selectedCategory = name)}
          >
            <!-- Voeg hier eventueel een icoon toe -->
            <span>{name}</span>
          </a>
        </li>
      {/each}
    </ul>
  </section>

  <!-- Inhoudssectie -->
  <section>
    {#each categories as { name, video, content }}
      {#if selectedCategory === name}
        <article>
          <iframe
            width="560"
            height="315"
            src={video}
            title={name}
            frameborder="0"
            allowfullscreen
          />

          <h2>{name}</h2>
          <p>{content}</p>
        </article>
      {/if}
    {/each}
  </section>
</main>

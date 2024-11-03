<script>
  export let address;
  export let title;
  export let subtitle;
  export let imageUrl;
  export let description;
  import Button from "../UI/Button.svelte";
</script>

<article>
  <div id="header">
    <h1>{title}</h1>
    <h2>{subtitle}</h2>
    <p>{address}</p>
  </div>
  <div class="image">
    <img width="100%" height="100%" src={imageUrl} alt="not found" />
  </div>
  <div class="content">
    <p>{description}</p>
  </div>
  <div id="buttons">

    <Button type='button' content="Show Details" variant='contain'/>
    <Button type='button' content="Contact" variant='outline'/>
    <Button type='button' content="Favorite" variant='contain'/>
  </div>
</article>

<style>
  article {
    width: 49%;
    background-color: white;
    border-radius: 1rem;
    color: black;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  }
  #header,
  .content,
  #buttons {
    padding: 1rem;
  }
  .image {
    height: 14rem;
    width: 100%;
  }
</style>

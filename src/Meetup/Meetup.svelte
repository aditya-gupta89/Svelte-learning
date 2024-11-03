<script>
  export let meetups;
  import MeetupItem from "./MeetupItem.svelte";
</script>

<section id="meetups">
  {#each meetups as meetup}
    <MeetupItem
      address={meetup.address}
      description={meetup.description}
      imageUrl={meetup.imageUrl}
      subtitle={meetup.subtitle}
      title={meetup.title}
    />
  {/each}
</section>

<style>
  #meetups {
    width: 90%;
    margin: auto;
    margin-top: 5rem;
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;

  }
</style>

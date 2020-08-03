<script>
  import { onMount } from "svelte";
  import { fadeIn, fadeOut } from "../components/Fade";

  onMount(() => {
    if (window.netlifyIdentity) {
      window.netlifyIdentity.on("init", user => {
        if (!user) {
          window.netlifyIdentity.on("login", () => {
            document.location.href = "/admin/";
          });
        }
      });
    }
  });
</script>

<style>
  h3 {
    font-size: 2rem;
    line-height: 1.4;
  }
</style>

<svelte:head>
  <title>Scott Tolinski - Level Up Tutorials & Syntax - Web Developer</title>
</svelte:head>

<div in:fadeIn out:fadeOut>
  <h1>Scott Tolinski</h1>
  <iframe
    width="560"
    height="315"
    src="https://www.youtube.com/embed/Q9eh2iJsjxE"
    frameborder="0"
    allow="accelerometer; autoplay; encrypted-media; gyroscope;
    picture-in-picture"
    allowfullscreen />
  <h3>
    Web Developer | Creator of Level Up Tutorials | Co-host of Syntax.fm |
    Father of 2 | Bboy | Robotops Crew | Youtuber | Tea Drinker | Tutorial Maker
    | Fan of physical activity | Former Music Major | Denverite | Michigander |
    Shaw Brothers Kung Fu Film Watcher | Handstander | Stretching enthusiast
  </h3>
</div>

<script>
  import Post from "./lib/components/Post.svelte";
  import Form from "./lib/components/Form.svelte";
  import LastUpdate from "./lib/components/LastUpdate.svelte";
  import { generateFavIcon } from "./lib/js/helpers";

  generateFavIcon("#35202e");
</script>

<aside>
  <h1>img:edtr</h1>
</aside>

<main>
  <header>
    <ul id="header__list">
      <li class="header__list-item">custom tool</li>
      <li class="header__list-item">asset editor</li>
      <li class="header__list-item">simple design</li>
    </ul>
  </header>

  <section id="notice">
    <h2>Introduction and user instructions</h2>
    <p>
      Clients often ask for a way to produce simple graphic assets by themselves
      after receiving new branding guidelines. This tool provides a basic yet
      effective framework to meet that need. It's designed to allow users to
      easily edit predesigned images by changing text and colors while adhering
      to rules that protect the integrity of the brand. It is set with a basic
      range of configuration options and can be easily modified and augmented.
      Edit the text and the colors of the post using the form below. Click on
      "download" when you’re done.
    </p>
  </section>

  <section id="timeline">
    <h2>Current state of your post</h2>
    <Post />
  </section>

  <section id="configuration">
    <h2>Set up basic configuration before download</h2>
    <p>
      The form below allows you to edit the title, post body content, and job
      details. This tool was originally built for a human resources client of
      mine. You can modify the color of the text and background using the color
      picker. Generate the final post when you're done by clicking on download.
      The dimensions of the current post are set to meet LinkedIn's graphic
      recommendations (2000x2000).
    </p>
    <Form />
  </section>

  <section id="terms">
    <h2>Terms</h2>
    <p>
      This website is developed using svelte (without sveltekit) and generates a
      bundle of static assets, allowing it to be hosted on any server. The tool
      is obviously free; you can play around with it, modify it, us it in your
      projects and so on. Sources are available on <a
        href="https://github.com/ambientmoxie/image-editor"
        target="_blank">github</a
      >. It is offered as-is and may contain bugs.
    </p>
  </section>

  <footer>
    <LastUpdate />
  </footer>
</main>

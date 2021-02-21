<script>
  import { linkedin, spotify, telegram } from "../constants/icons";
</script>

<section>
  <div class="content">
    <img class="logo" src="logo.svg" alt="Logo" />
    <div class="content__text">
      <h1>Dymion Fritz</h1>
      <h2>Software Engineer</h2>
      <ul>
        <li>
          <a href="#usps">My skills</a>
        </li>
      </ul>
      <div class="contact">
        <a href="https://t.me/DympyDev" target="_blank">{@html telegram}</a>
        <a href="https://www.linkedin.com/in/dympydev/" target="_blank">
          {@html linkedin}
        </a>
        <a href="https://open.spotify.com/user/1125492997" target="_blank">
          {@html spotify}
        </a>
      </div>
    </div>
  </div>
</section>

<style>
  section {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
  }

  .content {
    max-height: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  ul,
  li {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  ul {
    margin: 24px 0;
  }

  img.logo {
    height: 50%;
    width: 50%;
  }

  .contact {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 12px;
  }

  /* Global, as the svg is a part of the @html transformer from Svelte, and thus can't be scoped */
  :global(.contact svg) {
    width: 36px;
    height: 36px;
  }

  @media (orientation: landscape) and (max-height: 420px) {
    .content {
      flex-direction: row;
    }

    img.logo {
      height: 100%;
    }

    .content__text {
      width: 50%;
    }
  }
</style>

<script>
  const sellingPoints = {
    Frameworks: [
      {
        name: "Angular",
        icon: "usps/frameworks/angular.svg",
        yearsOfExperience: 4,
      },
      {
        name: "AngularJs",
        icon: "usps/frameworks/angularjs.svg",
        yearsOfExperience: 4,
      },
      {
        name: "Svelte",
        icon: "usps/frameworks/svelte.svg",
        yearsOfExperience: 1,
      },
      {
        name: "Polymer",
        icon: "usps/frameworks/polymer.svg",
        yearsOfExperience: 1,
      },
      {
        name: "React",
        icon: "usps/frameworks/react.svg",
        yearsOfExperience: 1,
      },
      {
        name: "Karma",
        icon: "usps/frameworks/karma.svg",
        yearsOfExperience: 6,
      },
      {
        name: "Jasmine",
        icon: "usps/frameworks/jasmine.svg",
        yearsOfExperience: 6,
      },
      {
        name: "Jest",
        icon: "usps/frameworks/jest.svg",
        yearsOfExperience: 1,
      },
      {
        name: "Cypress",
        icon: "usps/frameworks/cypress.svg",
        yearsOfExperience: 3,
      },
      {
        name: "Protractor",
        icon: "usps/frameworks/protractor.svg",
        yearsOfExperience: 4,
      },
    ],
    Languages: [
      {
        name: "Javascript",
        icon: "usps/languages/javascript.svg",
        yearsOfExperience: 11,
      },
      {
        name: "Typescript",
        icon: "usps/languages/typescript.svg",
        yearsOfExperience: 5,
      },
      {
        name: "Java",
        icon: "usps/languages/java.svg",
        yearsOfExperience: 5,
      },
      {
        name: "Objective-C",
        icon: "usps/languages/apple.svg",
        yearsOfExperience: 2,
      },
      {
        name: "Dart",
        icon: "usps/languages/dart.svg",
        yearsOfExperience: 1,
      },
      {
        name: "PHP",
        icon: "usps/languages/php.svg",
        yearsOfExperience: 3,
      },
      {
        name: ".NET",
        icon: "usps/languages/dotnet.svg",
        yearsOfExperience: 1,
      },
    ],
    "CI/CD": [
      {
        name: "Jenkins",
        icon: "usps/ci_cd/jenkins.svg",
        yearsOfExperience: 4,
      },
      {
        name: "Azure Pipelines",
        icon: "usps/ci_cd/azure-pipelines.svg",
        yearsOfExperience: 3,
      },
      {
        name: "Gitlab CI/CD",
        icon: "usps/ci_cd/gitlab.svg",
        yearsOfExperience: 2,
      },
    ],
    "Version control": [
      {
        name: "Git",
        icon: "usps/version_control/git.svg",
        yearsOfExperience: 9,
      },
      {
        name: "SVN",
        icon: "usps/version_control/svn.svg",
        yearsOfExperience: 3,
      },
    ],
    Tooling: [
      {
        name: "Jira",
        icon: "usps/tooling/jira.svg",
        yearsOfExperience: 6,
      },
      {
        name: "Azure Boards",
        icon: "usps/tooling/azure-boards.svg",
        yearsOfExperience: 3,
      },
    ],
    Hobbies: [
      {
        name: "Playing games",
        icon: "usps/hobbies/steam.svg",
      },
      {
        name: "Drinking beers",
        icon: "usps/hobbies/hertog-jan.svg",
      },
      {
        name: "Learning new stuff",
        icon: "usps/hobbies/udemy.svg",
      },
    ],
  };
</script>

<section>
  <header>
    <h1>USP overzicht</h1>
    <a href="#home">Back home</a>
  </header>
  <div class="skill-overview">
    {#each Object.keys(sellingPoints) as usp}
      <h2>{usp}</h2>
      <div class="skills">
        {#each sellingPoints[usp] as uspItem}
          <div class="usp">
            {#if uspItem.icon}
              <img src={uspItem.icon} alt={uspItem.icon} />
            {/if}
            <h3>{uspItem.name}</h3>
            {#if uspItem.yearsOfExperience}
              <h4>{uspItem.yearsOfExperience}+ years</h4>
            {/if}
          </div>
        {:else}
          <p>Oops, nothing yet! But keep watching this space!</p>
        {/each}
      </div>
    {/each}
  </div>
</section>

<style>
  header {
    height: 64px;
    display: flex;
    align-items: center;
    border-bottom: 1px solid var(--raisinBlack);
  }

  header > h1 {
    margin: 0;
    padding: 0;
  }

  header,
  .skills {
    margin: 0 8px;
  }

  a {
    margin-left: auto;
  }

  .skill-overview {
    overflow: auto;
    height: calc(100vh - 64px);
    overflow: auto;
  }

  h2 {
    margin: 0.5em;
    margin-top: 1em;
  }

  .skills {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
  }

  .skills:last-child {
    margin-bottom: 1em;
  }

  .usp {
    background-color: #fff;
    border-radius: 24px;
    height: 256px;
    text-align: center;
    display: grid;
    grid-template-rows: 70% 15% 15%;
  }

  .usp > img {
    max-width: 90%;
    max-height: 128px;
    align-self: center;
    justify-self: center;
  }

  @media (max-width: 420px) {
    .skills {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>

<script lang='ts'>
  const burger = (node: HTMLElement): SvelteActionReturnType => {
    const clickCallback = () => {
      const target = document.querySelector(node.dataset.target)
      node.classList.toggle("is-active")
      target.classList.toggle("is-active")
    }
    node.addEventListener("click", clickCallback)
    return {
      destroy() {
        node.removeEventListener("click", clickCallback)
      }
    }
  }
</script>
<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" width="112" height="28" alt="Bulma logo">
    </a>

    <button role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="#siteNavbarNavMenuContent" use:burger>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </button>
  </div>

  <div id="siteNavbarNavMenuContent" class="navbar-menu">
    <div class="navbar-start">
      <a class="navbar-item" href="/">
        Home
      </a>

      <a class="navbar-item" href="/">
        Documentation
      </a>

      <div class="navbar-item has-dropdown is-hoverable">
        <a class="navbar-link" href="/">
          More
        </a>

        <div class="navbar-dropdown">
          <a class="navbar-item" href="/">
            About
          </a>
          <a class="navbar-item" href="/">
            Jobs
          </a>
          <a class="navbar-item" href="/">
            Contact
          </a>
          <hr class="navbar-divider">
          <a class="navbar-item" href="/">
            Report an issue
          </a>
        </div>
      </div>
    </div>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <a class="button is-primary" href="/">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light" href="/">
            Log in
          </a>
        </div>
      </div>
    </div>
  </div>
</nav>
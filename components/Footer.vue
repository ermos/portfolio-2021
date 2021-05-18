<template>
  <footer id="footer">
    <nav class="contact">
      <a href="https://github.com/ermos">
        <fa :icon="['fab', 'github']" />
      </a>
      <a href="https://www.linkedin.com/in/kilian-smiti-106556148/"
        ><fa :icon="['fab', 'linkedin']"
      /></a>
      <a href="mailto:kilian.smiti@outlook.fr">
        <fa :icon="['fas', 'envelope']" />
      </a>
    </nav>
    <p class="copyright">&copy; 2021 - Kilian SMITI</p>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
}
</script>

<style>
#footer {
  width: 100%;
  background-color: var(--sub-color);
  color: #fff;
  display: flex;
  flex-direction: column;
}

.contact {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: #fff;
  margin: auto;
  flex: 1;
}

.contact a {
  display: block;
  padding: var(--spacing-little);
  text-decoration: none;
  color: inherit;
}

.contact a:hover {
  transition: all 0.4s ease-in;
  color: var(--neutral-color);
}

.contact svg {
  font-size: 4rem;
}

.copyright {
  font-weight: bold;
  color: #fff;
  text-align: center;
  font-size: 1.7rem;
  padding: var(--spacing-medium);
}
</style>

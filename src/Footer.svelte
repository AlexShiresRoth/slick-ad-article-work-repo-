<script>
  // your script goes here
</script>

<style type="text/scss">
  /* your styles go here */
  .footer {
    width: 100%;
    background: #e3658918;
    padding: 2rem 0;
    margin-top: 2rem;
    min-height: 10vh;
    &__inner {
      width: 90%;
      display: flex;
      justify-content: center;
      align-items: center;
      & img {
        max-width: 9rem;
      }
      & p,
      & a {
        color: #666;
        margin: 0 0.5rem;
      }
    }
  }
  @media screen and (max-width: 900px) {
    .footer {
      width: 100%;
      background: #e3658918;
      padding: 2rem 0;
      margin-top: 2rem;
      min-height: 10vh;
      &__inner {
        width: 90%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        & img {
          max-width: 9rem;
        }
        & p {
          color: #666;
        }
      }
    }
  }
</style>

<footer class="footer">
  <div class="footer__inner">
    <img src="https://ik.imagekit.io/usam13ogl7u/bd-logo_UEh9PReIR.png" />
    <p>Beauty Discoveries</p>
    <p>&copy; 2020</p>
    <a
      href="https://slick.love/pages/privacy-policy"
      target="_blank"
      rel="noopener noreferrer">
      Privacy Policy
    </a>
    <a
      href="https://slick.love/pages/contact-us"
      target="_blank"
      rel="noopener noreferrer">
      Contact Us
    </a>
  </div>
</footer>

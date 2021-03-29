<script>
  import Icon from "svelte-awesome";
  import {
    facebook,
    instagram,
    youtube,
    pinterest,
    envelope,
  } from "svelte-awesome/icons";
  let author = "Kate Wingham";
  const fetchAnAvatar = async () => {
    const res = await fetch("https://randomuser.me/api/?gender=female", {
      headers: {
        "Access-Control-Allow-Origin": "http://localhost:5000",
        "Content-Type": "application/json",
      },
    })
      .then((response) => response.json())
      .catch((err) => err);

    return res;
  };
</script>

<header class="header">
  <div class="header__inner">
    <div class="story-title">
      <h1>
        The Hottest Trend of 2021 Is Magnetic Lashes, Here’s All You Need To
        Know And How To Save Big On Trying Them.
      </h1>

      <div class="caption">
        <p>Published December 21, 2020</p>
        <div class="author">
          <p>By: {author}</p>
          {#await fetchAnAvatar()}
            <p>Loading Image...</p>
          {:then res}
            <img src={res.results[0].picture.thumbnail} alt={author} />
          {:catch error}
            {console.log(error)}
            <p>Looks like there was an error loading the image</p>
          {/await}
        </div>
        <!-- <div class="icons">
                    <Icon
                        data={facebook}
                        style="margin-right: .2rem; color:#932f6d" />
                    <Icon
                        data={instagram}
                        style="margin:0 .2rem; color:#932f6d" />
                    <Icon
                        data={youtube}
                        style="margin:0 .2rem; color:#932f6d" />
                    <Icon
                        data={pinterest}
                        style="margin:0 .2rem; color:#932f6d" />
                    <Icon
                        data={envelope}
                        style="margin:0 .2rem; color:#932f6d" />
                </div> -->
      </div>
    </div>
  </div>
</header>

<style type="text/scss">
  $background-color-faded: #932f6d69;
  $background-color: #932f6d;
  .header {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    &__inner {
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 2rem 0;
      & .story-title {
        max-width: 75%;
        & h1 {
          margin-top: 0;
          color: #342e37;
          position: relative;
          &::after {
            width: 90%;
            content: " ";
            height: 3px;
            background: $background-color;
            display: block;
            margin-top: 1rem;
          }
        }
        & .caption {
          display: flex;
          flex-direction: column;
          & p {
            margin: 0;
            color: #666;
            font-weight: 700;
          }
          & .author {
            display: flex;
            align-items: center;
            margin: 0.5rem 0;
            & img {
              border-radius: 50%;
              max-width: 1.5rem;
              margin-left: 0.5rem;
            }
          }
          & .icons {
            display: flex;
            align-items: center;
            & svg {
              margin: 0 0.5rem;
            }
          }
        }
      }
    }
  }
  @media screen and (max-width: 900px) {
    .header {
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 6rem;
      &__inner {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1rem 0;
        & .story-title {
          max-width: 95%;
          & h1 {
            margin-top: 0;
            color: #342e37;
            position: relative;
            font-size: 1.4rem;
          }
        }
      }
    }
  }
</style>

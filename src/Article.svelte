<script>
    // your script goes here
    const steps = [
        {
            stepNum: "Step 1",
            direction: ` Draw a line above your eyelid (make dots and
                        connect them if drawing a line is tough)`,
            img: "https://ik.imagekit.io/usam13ogl7u/step1_pWqn6nYdPK.png",
        },
        {
            stepNum: "Step 2",
            direction: `Let it dry then apply a second line`,
            img: "https://ik.imagekit.io/usam13ogl7u/step2_raCdPEFbr.png",
        },
        {
            stepNum: "Step 3",
            direction: `Once 90% dry apply the lash… Wait`,
            img: "https://ik.imagekit.io/usam13ogl7u/step3_q8HSoGvJw.png",
        },
    ];
</script>

<style type="text/scss">
    $background-color-faded: #932f6d69;
    $background-color: #932f6d;
    .article-container {
        width: 100%;
        display: flex;
        flex-direction: column;
    }
    .article-content {
        width: 100%;
        display: flex;
        justify-content: space-between;
        & .column-left {
            width: 60%;
            & .image-hero-box {
                max-width: 100%;
                & img {
                    max-height: 20rem;
                    object-fit: cover;
                    width: 100%;
                }
            }
            & .img-box {
                max-width: 100%;
                & img {
                    width: 100%;
                    object-fit: contain;
                }
            }
            & .steps-grid {
                display: grid;
                grid-template-columns: repeat(3, 1fr);
                gap: 1rem;
                width: 100%;
                & .column {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    padding: 1rem 0;
                    box-shadow: 0 1px 5px rgba(100, 100, 100, 0.281);
                    &__heading {
                        width: 100%;
                        padding: 0.5rem 0;
                        border-bottom: 1px solid #eee;
                        & h4 {
                            color: $background-color;
                            margin: 0;
                            margin-left: 1rem;
                        }
                    }
                    & p {
                        margin: 0.5rem 1rem;
                        color: #333;
                        max-width: 70%;
                    }
                    & img {
                        object-fit: cover;
                        width: 100%;
                    }
                }
            }
        }
        & .full-width {
            width: 100%;
        }
        & .column-right {
            width: 30%;
        }
    }
</style>

<section class="article-container">
    <div class="article-content">
        <div class="column-left">
            <p>
                <strong>Magnetic lashes have forever changed my life</strong>
                and after using them
                <strong>I am sure they will forever change yours too.</strong>
            </p>
            <p>
                Let’s face it,
                <strong>girls with long lashes get the smiles and attention.</strong>
                My friend who pays $150 plus tip every 4 weeks and has the best
                eyelashes ever is
                <strong>always getting attention and compliments on her eye’s</strong>.
                Most people do not even realize why, they are just drawn to
                them.
            </p>
            <div class="image-hero-box">
                <img
                    src="https://ik.imagekit.io/usam13ogl7u/eyelash-sdfsdf_prv5PlUyYz.jpg" />
            </div>
            <p>
                <strong>I wanted that attention too but unlike her, I am not
                    willing to go deep into debt</strong>
                paying $150+ a month on eyelashes, so I gave up.
            </p>
            <p>
                Then
                <strong>like always my phone came to my rescue and Facebook
                    showed me an ad for these magnetic lashes that you can do at
                    home.</strong>
                I was an easy sell, magnetic lashes that can be worn 20-30 times
                and put on at home for under $20?
            </p>
            <p>
                <a href="https://freelashkit.com"><strong>Sign me up!</strong></a>
            </p>
            <p>So I did and a few days later they came.</p>
            <div class="img-box">
                <img
                    src="https://ik.imagekit.io/usam13ogl7u/V1nISPlet_mid_sG4nhwBpZ.jpg" />
            </div>
            <p>
                Oh how glorious. Then it settled in,
                <strong>what did I get myself in to … they said it was easy but
                    would it be?</strong>
            </p>
        </div>
        <div class="column-right">
            <div
                class="fb-post"
                data-href="https://www.facebook.com/Slick.Love.Lashes/posts/230103438522532"
                data-width="350"
                data-show-text="true">
                <blockquote
                    cite="https://www.facebook.com/Slick.Love.Lashes/posts/230103438522532"
                    class="fb-xfbml-parse-ignore">
                    <p>
                        Get Our Premium Magnetic Lash Kit at a HUGE Discount.
                        Arrives in 3-9 Days
                    </p>Posted by
                    <a
                        href="https://www.facebook.com/Slick.Love.Lashes/">Slick</a>
                    on&nbsp;<a
                        href="https://www.facebook.com/Slick.Love.Lashes/posts/230103438522532">Monday,
                        December 21, 2020</a>
                </blockquote>
            </div>
        </div>
    </div>
</section>
<section class="article-container">
    <div class="article-content">
        <div class="column-left full-width">
            <p><strong>So I followed the directions</strong></p>
            <div class="steps-grid">
                {#each steps as { stepNum, direction, img }, i}
                    <div class="column">
                        <div class="column__heading">
                            <h4>{stepNum}</h4>
                        </div>
                        <p>{direction}</p>
                        <img src={img} alt="step one" />
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>

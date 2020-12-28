<script>
    import Icon from "svelte-awesome";
    import { bars, close } from "svelte-awesome/icons";
    import { writable } from "svelte/store";

    let hidden = writable(true);

    let hidden_value;

    const handleMenuToggle = (bool) => {
        // let bool = hidden.subscribe((value) => value);
        hidden.update((val) => (val = bool));
    };

    const unsub = hidden.subscribe((value) => {
        console.log("this si the value" + value);
        hidden_value = value;
    });
</script>

<style type="text/scss">
    .nav {
        box-shadow: 0 1px 4px #eee;
        display: flex;
        justify-content: center;
        width: 100%;
        align-items: center;
        padding: 0.5rem 0;
        &__inner {
            width: 75%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            &__nav-left {
                display: flex;
                align-items: center;
                & img {
                    max-width: 8rem;
                }
                & h2 {
                    color: #666;
                    font-weight: 100;
                    font-size: 1.2rem;
                }
            }
            &__nav-right {
                display: flex;
                & a {
                    text-decoration: none;
                    margin: 0 0.5rem;
                    font-weight: 700;
                    color: #f18e81;
                }
            }
        }
    }
    .mobile_nav,
    .mobile_menu,
    .mobile_menu_hidden {
        display: none;
    }
    @media screen and (max-width: 900px) {
        .nav {
            display: none;
        }
        .mobile_nav {
            box-shadow: 0 1px 4px #eee;
            display: flex;
            justify-content: center;
            width: 100%;
            align-items: center;
            padding: 0.5rem 0;
            position: fixed;
            top: 0;
            left: 0;
            background: #fbfbfb;
            z-index: 99999999;
            &__inner {
                display: flex;
                justify-content: space-between;
                align-items: center;
                width: 90%;
                &__nav-left {
                    display: flex;
                    align-items: center;
                    & img {
                        max-width: 6rem;
                    }
                    & h2 {
                        color: #342e37;
                    }
                }
                &__nav-right {
                    display: flex;
                    & a {
                        text-decoration: none;
                        margin: 0 0.5rem;
                        font-weight: 700;
                        color: #f18e81;
                    }
                    & button {
                        background: transparent;
                        border: 0;
                        font-size: 2rem;
                        & svg {
                            font-size: 1.5rem;
                            width: 2rem;
                            scale: 2rem;
                        }
                    }
                }
            }
        }

        .mobile_menu_hidden {
            transform: translateY(-100vh);
            position: absolute;

            z-index: 222;
            position: absolute;
            height: 100vh;
            width: 100%;
            background: #fff;
            transition: all 1s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        .mobile_menu {
            transform: translateY(0);
            z-index: 222;
            position: absolute;
            height: 100vh;
            width: 100%;
            background: #fff;
            transition: all 1s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            & a {
                font-size: 1.2rem;
                color: #f18e81;
                font-weight: 700;
                margin: 1rem 0;
            }
        }
    }
</style>

<nav class="nav">
    <div class="nav__inner">
        <div class="nav__inner__nav-left">
            <img
                src="https://ik.imagekit.io/usam13ogl7u/bd-logo_UEh9PReIR.png" />
            <h2>Beauty Discoveries | Advertorial</h2>
        </div>
        <div class="nav__inner__nav-right">
            <a href="https://www.freelashkit.com">Get Started</a><a
                href="https://www.freelashkit.com">Lashes</a>
        </div>
    </div>
</nav>
<nav class="mobile_nav">
    <div class="mobile_nav__inner">
        <div class="mobile_nav__inner__nav-left">
            <img
                src="https://ik.imagekit.io/usam13ogl7u/bd-logo_UEh9PReIR.png" />
        </div>
        <div class="mobile_nav__inner__nav-right">
            <button on:click={() => handleMenuToggle(!hidden_value)}>
                {#if hidden_value}
                    <Icon data={bars} scale={'1.4'} />
                {/if}
                {#if !hidden_value}
                    <Icon data={close} scale={'1.4'} />
                {/if}</button>
        </div>
    </div>
</nav>
<div class={hidden_value ? 'mobile_menu_hidden' : 'mobile_menu'}>
    <a href="">Get Started</a><a href="">Lashes</a>
</div>

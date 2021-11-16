<script type="ts">
    import { onMount } from "svelte";

    import Header from "../components/Header.svelte";

    let mounted = false;
    onMount(() => {
        mounted = true;
    });
</script>

<Header />

<div id="wrapper">
    <div id="img-wrapper">
        <img id="logo" src="logo.png" alt="AIMS" />
    </div>
    <main>
        <article class={mounted ? "fade-in" : ""}>
            <h1>We aim to...</h1>
            <div class="promise">
                <h3><i class="icofont-clock-time" /> Save You Time</h3>
                <p>
                    We provide accurate and real time inventory management of
                    controlled substances in your business so you can focus less
                    on the process and more on the product.
                </p>
            </div>
            <div class="promise">
                <h3>
                    <i class="icofont-chart-growth" /> Optimize Your Operations
                </h3>
                <p>
                    We integrate data management seamlessly into your
                    productions process to optimize your production time and
                    provide streamlined methods of generating controlled
                    substance reports.
                </p>
            </div>
        </article>
        <article class={mounted ? "fade-in" : ""}>
            <h1>Our Team</h1>
            <div class="member">
                <img
                    src="profiles/charles-jolin-landry.jpg"
                    alt="Charles Jolin-Landry"
                />
                <div>
                    <h3>Charles Jolin-Landry</h3>
                    <p>
                        Charles earned a Master’s degree in mathematics from the
                        University of British Columbia and founded Bitmotek
                        Optimization Ltd. with the purpose of bringing
                        mathematical optimization to businesses in needs of
                        solving logistical and combinatorial problems standing
                        in the way of growth and efficiencies.
                    </p>
                </div>
            </div>
            <div class="member">
                <img src="profiles/anesh-pillai.jpg" alt="Anesh Pillai" />
                <div>
                    <h3>Anesh Pillai</h3>
                    <p>
                        Anesh is a business owner and project manager with
                        experience in both technological fields and logistics.
                        Add additional info here...
                    </p>
                </div>
            </div>
            <div class="member">
                <img src="profiles/trevor-richard.jpg" alt="Trevor Richard" />
                <div>
                    <h3>Trevor Richard</h3>
                    <p>
                        Trevor Richard is a full-stack website developer and
                        avid programmer who focuses on the creative side of
                        technology and human computer interaction in web
                        development.
                    </p>
                </div>
            </div>
        </article>
    </main>
</div>

<style>
    #wrapper {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        overflow: auto;
        background-image: radial-gradient(
            farthest-side at center 20%,
            var(--bg-color) 0,
            var(--bg-color) 30%,
            var(--shadow-color) 100%
        );
    }
    #img-wrapper {
        height: 30%;
        min-height: max-content;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2em;
        padding-bottom: 0;
    }
    #logo {
        max-width: 80%;
    }
    main {
        padding: 0 25%;
    }
    article {
        position: relative;
        opacity: 0;
        top: 160px;
        transition: all 1.2s ease-out;
        margin-bottom: 5em;
        margin-top: 2em;
    }
    article.fade-in {
        opacity: 1;
        top: 0;
    }

    article h1 {
        margin-top: 0;
        text-align: center;
        padding: 7px;
        background-color: var(--shadow-color);
        background: linear-gradient(
            to right,
            #eee0,
            var(--shadow-color),
            #eee0
        );
        color: var(--text-color);
        text-shadow: 2px 2px 1px var(--bg-color);
        border-top: 2px solid var(--accent-color);
        border-bottom: 2px solid var(--accent-color);
    }

    .promise {
        border-radius: 3px;
        margin: 1em;
        overflow: hidden;
        border: 1px solid var(--accent-color);
    }

    .promise h3 {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        margin: 0;
        padding: 14px;
        background-color: var(--accent-color);
        color: var(--bg-color);
    }

    .promise h3 > i {
        font-size: 24px;
        margin-right: 12px;
    }

    .promise p {
        margin: 0;
        padding: 14px;
        background-color: var(--bg-color);
        color: var(--text-color);
    }

    .member {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        margin: 2em 0;
    }

    .member > img {
        margin-right: 2em;
        width: 80px;
        height: 80px;
        border-radius: 50%;
        image-rendering: optimizeQuality;
        box-shadow: 2px 2px 7px #ccc;
    }

    .member > div {
        border-left: 2px solid var(--accent-color);
        padding-left: 2em;
    }

    .member h3 {
        color: var(--accent-color);
    }

    @media screen and (max-width: 1600px) {
        main {
            padding: 0 20%;
        }
    }

    @media screen and (max-width: 1024px) {
        main {
            padding: 0 10%;
        }
    }

    @media screen and (max-width: 640px) {
        #img-wrapper {
            height: 20%;
        }

        #logo {
            max-width: 100%;
        }

        main {
            padding: 0 1em;
        }

        .member {
            display: block;
            text-align: center;
        }

        .member > img {
            flex-grow: 1;
            margin-right: 0;
        }

        .member > div {
            border-left: none;
            padding: 1em;
        }
    }
</style>

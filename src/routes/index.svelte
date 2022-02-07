<script type="ts">
    import { onMount } from "svelte";
    import Header from "$src/components/Header.svelte";

    // Booking Link
    const bookingLink = "https://outlook.office365.com/owa/calendar/AIMS1@bitmotek.ca/bookings/";

    let mounted = false;
    onMount(() => {
        mounted = true;
    });
</script>

<div id="wrapper">
    <Header />
    <div id="container">
        <div id="img-wrapper">
            <img id="logo" src="logo.png" alt="AIMS" />
        </div>
        <main>
            <article class={mounted ? "fade-in" : ""}>
                <div class="promise">
                    <h3><i class="icofont-search-2" /> Discover AIMS!</h3>
                    <p>
                        We are now offering <a href="#booking">flexible bookings</a> to meet with our team members!
                    </p>
                </div>
            </article>
            <article class={mounted ? "fade-in" : ""}>
                <h1>We Aim to...</h1>
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
                <div class="promise">
                    <h3>
                        <i class="icofont-lock" /> Keep Your Data Safe
                    </h3>
                    <p>
                        Your privacy is our concern and AIMS will never leverage or
                        sell the data that you trust with us.
                    </p>
                </div>
            </article>
            <article id="team" class={mounted ? "fade-in" : ""}>
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
                            He leverages his experience in team management to bring
                            goals to realities.
                        </p>
                    </div>
                </div>
                <div class="member">
                    <img src="profiles/trevor-richard.jpg" alt="Trevor Richard" />
                    <div>
                        <h3>Trevor Richard</h3>
                        <p>
                            Trevor is a full-stack website developer and avid
                            programmer who focuses on the creative side of
                            technology and human computer interaction in web
                            development.
                        </p>
                    </div>
                </div>
            </article>
            <article id="booking" class={mounted ? "fade-in" : ""}>
                <h1>Discover AIMS</h1>
                <div>
                    <div>
                        <p>
                            We are looking to discover more about the alcohol industry and the difficulties that businesses face on a daily basis. We want to hear what <i>you</i> are looking for to improve your business, and are offering flexible bookings with our team members to discuss how we can help you reach your goals. <a href={bookingLink}>Book a meeting now!</a>
                        </p>
                        <p>
                            Looking forward to talking with you,<br>
                            <strong>The AIMS Team</strong>
                        </p>
                    </div>
                    <div>
                        <a href={bookingLink} id="booking-link"><button>Book a Discovery Meeting!</button></a>
                    </div>
                </div>
            </article>
        </main>
    </div>
</div>

<style>
    #wrapper {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-image: radial-gradient(
            farthest-side at center 20%,
            var(--bg-color) 0,
            var(--bg-color) 30%,
            var(--bg-color-2) 100%
        );
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: stretch;
    }
    #container {
        overflow: auto;
        flex-grow: 1;
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
    #booking-link {
        text-decoration: none;
        display: inline-block;
        margin: 1rem 0;
    }
    #booking-link>button {
        background-color: var(--accent-color);
        color: var(--bg-color);
        font-weight: bold;
        font-size: 18px;
        padding: 1rem 1rem;
        border-radius: 0.25rem;
    }
    main {
        padding: 0 25%;
        padding-bottom: 10rem;
    }
    article {
        position: relative;
        opacity: 0;
        top: 160px;
        transition: all 1.2s ease-out;
        margin-bottom: 5em;
        margin-top: 1em;
        padding-top: 1em;
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
            var(--bg-color),
            #eee0
        );
        color: var(--text-color);
        text-shadow: 1px 1px 1px #ccc;
        border-top: 2px solid var(--accent-color);
        border-bottom: 2px solid var(--accent-color);
    }

    .promise {
        border-radius: 3px;
        margin: 1em 0.2em;
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
        width: 96px;
        height: 96px;
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
            height: 15%;
            padding: 3em;
            padding-bottom: 0;
        }

        #logo {
            max-width: 80%;
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

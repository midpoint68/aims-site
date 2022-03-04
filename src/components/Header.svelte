<script type="ts">
    export let title = "AIMS - Alcohol Inventory Management System";
    let showMenu = false;
</script>

<svelte:head>
    <title>{title}</title>
</svelte:head>

<svelte:body on:click={()=>{ if(showMenu) showMenu = false; }}></svelte:body>

<header>
    <nav>
        <a href="/">
            <img id="logo" src="logo.png" alt="AIMS">
        </a>
        <div id="mobile-links" on:click={(e) => { e.stopPropagation(); showMenu = !showMenu; }}><i class="icofont-navigation-menu"></i></div>
        <div id="links" class:show={showMenu}>
            <a class="link" href="/#team">Team</a>
            <a class="link" href="/#booking">Discover</a>
        </div>
    </nav>
</header>

<style>
    header {
        background-color: var(--bg-color);
    }
    nav {
        position: relative;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: space-between;
        align-items: center;
        box-shadow: 2px 2px 7px var(--shadow-color);
        padding: 1rem;
    }
    #logo {
        height: 32px;
        cursor: pointer;
    }
    #mobile-links {
        display: none;
    }
    #links {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: flex-start;
        align-items: stretch;
        z-index: 2;
    }
    #links a {
        color: var(--accent-color);
        font-weight: bold;
        text-decoration: none;
        display: inline-block;
        margin: 0 0.5rem;
        border-radius: 3px;
        background-color: var(--bg-color);
        border: 1px solid var(--bg-color-2);
        padding: 0.5rem 1rem;
        box-shadow: 0 0 0 var(--shadow-color);
        transition-property: transform, box-shadow;
        transition-duration: 0.2s;
        transition-timing-function: ease-out;
    }
    #links a:visited {
        color: var(--accent-color);
    }
    #links a:hover {
        transform: translate(-1px, -1px);
        box-shadow: 2px 2px 5px var(--shadow-color);
    }

    @media screen and (max-width: 640px) {
        #mobile-links {
            display: block;
            font-size: 28px;
            color: var(--accent-color);
            cursor: pointer;
        }
        #links {
            display: none;
            flex-direction: column;
            position: absolute;
            top: 90%;
            right: 0.5rem;
            box-shadow: 2px 2px 7px var(--shadow-color);
        }
        #links.show {
            display: flex;
        }
        #links > .link {
            border-radius: 0;
            margin: 0;
        }
    }
</style>
<script>
    import { onMount } from "svelte";
    import { staticData } from "./stores/staticData.js";
    import Router from "svelte-spa-router";
    import { wrap } from "svelte-spa-router/wrap";
    import Header from "./comps/ui/Header.svelte";
    //importing pages
    import Home from "./comps/pages/Home.svelte";
    import About from "./comps/pages/About.svelte";
    import Contact from "./comps/pages/Contact.svelte";
    import Footer from "./comps/ui/Footer.svelte";
    import Sidebar from "./comps/ui/Sidebar.svelte";
    import Members from "./comps/pages/Members.svelte";
    import Events from "./comps/pages/Events.svelte";
    import Blogs from "./comps/pages/Blogs.svelte";

    onMount(async () => {
        await fetch("data/data.json")
            .then((res) => {
                if (!res.ok) {
                    throw new Error(
                        "Problem fetching site data: " + res.status
                    );
                } else {
                    return res.json();
                }
            })
            .then((data) => {
                $staticData = data;
            })
            .catch((err) => console.log(err));
    });
    let routes = {
        "/": Home,
        "/blogs": Blogs,
        "/events": Events,
        "/members": Members,
        "/about": About,
        "/contact": Contact,
    };
</script>

<div class="header">
    <Header />
</div>

<main class="container">
    <main class="main-content">
        <div class="pages">
            <Router {routes} />
        </div>
        <div class="sidebar">
            <Sidebar />
        </div>
    </main>
    <footer>
        <Footer />
    </footer>
</main>

<style>
    .container {
        width: 100%;
        margin: auto;
        position: relative;
        padding: 0 20px;
        max-width: 1200px;
    }
    .header {
        width: 100%;
        margin: auto;
        background: rgb(252, 250, 250);
        box-shadow: 0 1px 0 rgb(194, 189, 189);
        position: sticky;
        top: 0;
        z-index: 20;
    }
    .main-content {
        padding: 20px 0;
        display: grid;
        grid-template-columns: 3fr 1fr;
        grid-column-gap: 20px;
        min-height: 80vh;
    }
    @media (max-width: 700px) {
        .main-content {
            grid-template-columns: 1fr;
        }
    }
</style>

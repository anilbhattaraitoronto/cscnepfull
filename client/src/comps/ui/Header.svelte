<script>
</script>

<main>
    <header>
        <a href="#/" class="masthead-link">
            <h1 class="masthead">CSC</h1>
        </a>
        <nav>
            <a href="#/" class="home-link">🏡</a>
            <a href="#/blogs">Blogs</a>
            <a href="#/events">Events </a>
            <a href="#/members">Members </a>
        </nav>
    </header>
</main>

<style>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        max-width: 1200px;
        margin: auto;
        padding: 16px 0;
    }
    header h1 {
        margin-left: 20px;
    }
    a {
        display: inline-block;
        margin-right: 16px;
    }

    .masthead-link,
    .home-link {
        text-decoration: none;
        transition: 200ms all ease-in-out;
        border: 1px solid transparent;
    }
    .masthead-link:hover,
    .home-link:hover {
        transform: scale(1.03);
        color: darkblue;
        border-color: rgb(238, 233, 233);
    }
    .masthead {
        text-align: center;
        font-size: calc(3vw + 10px);
        letter-spacing: 12px;
        color: rgb(101, 99, 99);
    }
    .masthead::after {
        content: "Chitwan in Canada";
        display: block;
        font-size: 12px;
        color: red;
        font-style: italic;
        letter-spacing: 1px;
        font-weight: 400;
    }
</style>

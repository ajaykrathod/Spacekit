<script>
import { goto } from '$app/navigation';

    import '../styles/global.css'
</script>

<header>
    <nav>
        <h2 on:click="{() => goto('/')}">
            Spacekit
        </h2>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
            <li>
                <a href="/apis">API's</a>
            </li>
            <li>
                <a href="/about">About</a>
            </li>
        </ul>
    </nav>
</header>

<main>
    <slot></slot>
</main>



<style>
    nav {
        width: 100vw;
        position: fixed;
        top: 0;
        height: 7vh;
        padding: 0 3vw;
        display: flex;
        z-index: 1;
        align-items: center;
        justify-content: space-between;
        left: 0;
        background-color: blanchedalmond;
    }
    ul {
        display: flex;
        width: 40vw;
        justify-content: space-evenly;
    }
    li{
        list-style: none;
    }

    h2 {
        cursor: pointer;
    }

    li a {
        text-decoration: none;
        color: black;
        font-size: large;
    }
</style>
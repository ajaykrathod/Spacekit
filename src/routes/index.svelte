<script context="module">
    /** @type {import('./__types/__layout').Load} */
    export async function load({fetch}) {
        const res = await fetch(`https://api.nasa.gov/planetary/apod?api_key=${import.meta.env.VITE_NASA_API_KEY}`)
        const apod = await res.json()

        if(res.ok){
            return{
                props : {
                    apod
                }
            }
        }

        return {
            status:res.status,
            error: new Error('Error Fetching APOD')
        }
    }
</script>

<script>
// @ts-nocheck
    import Footer from "../components/footer.svelte";
    export let apod;

</script>
{#if apod}
    <div class="apod" style="background: url({apod.url});background-size:cover;background-size:no-repeat;">
        <h1>APOD: Astronomy Picture of the Day.</h1>
        <h1>{apod.title}</h1>
        <div class="details">
            <div class="date">{apod.date}</div>
            <div class="author">{apod.copyright}</div>
        </div>
        <div class="explanation">{apod.explanation}</div>
        <Footer/>
    </div>
{/if}

<style>
    .apod {
        position: relative;
        top: 7vh;
        height: 93vh;
        overflow: hidden;
        display: flex;
        color: white;
        flex-direction: column;
    }

    .explanation, .details {
        margin: 2vh 5vw;
        text-align: center;
        font-weight: 600;
        font-size: x-large;
        line-height: 3vh;
    }

    .details {
        text-align: initial;
    }
    h1 {
        margin: 5vh auto 2vh auto;
    }
</style>

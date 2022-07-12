
<script>
// @ts-nocheck

    let date,longitude,lattitude
    let assets;
    const getData = async() => {
        // `https://api.nasa.gov/planetary/earth/assets?lon=${longitude}&lat=${lattitude}&date=${date}&dim=0.15&api_key=${import.meta.env.VITE_NASA_API_KEY}`
        const res = await fetch(`https://api.nasa.gov/planetary/earth/assets?lon=100.75&lat=1.5&date=2014-02-01&dim=0.15&api_key=${import.meta.env.VITE_NASA_API_KEY}`,{
            mode: 'cors',

        })
        const result =  await res.json()
        console.log(result);
        return result
        // https://api.nasa.gov/planetary/earth/assets?lon=100.75&lat=1.5&date=2014-02-01&dim=0.15&api_key=DEMO_KEY
    }
    const handleClick = () => {
        const promise = getData()
        promise.then(data => {
            assets = data;
        })
        .catch(err => console.log(err))
    }

</script>

<div class="container">
    <h2>
        Assets
    </h2>
    <div class="form">
        <input type="date" bind:value="{date}" name="Date" id="date">
        <input type="number" bind:value="{longitude}" placeholder="Enter Longitude" name="longitude" id="">
        <input type="number" bind:value="{lattitude}" placeholder="Enter Lattitude" name="lattitude" id="">
        <button type="submit" on:click="{handleClick}">Submit</button>
    </div>
</div>

{#if assets}
    <img src={assets.url} alt="">
{/if}


<style>
    h2 {
        margin: auto;
        font-size: xx-large;
    }
    .container {
        position: relative;
        top: 8vh;
        width: 100vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }
    .form {
        display: flex;
        flex-direction: column;
        max-width: 60vw;
        margin: 2vh auto;
        padding: 4vh 5vw;
        border-radius: 20px;
        border: 1px solid gray;
    }
    input , button{
        width: 50vw;
        line-height: 4vh;
        font-family: 'VT323', monospace;
        font-size: large;
        background: none;
        outline: none;
        border: 1px solid gray;
        border-radius: 20px;
        padding: 3px 10px;
        margin: 1vh 0;
    }
    img {
        margin: 10vh 0 0 0;
        width: 100vw;
        height: 100vh;
    }
</style>
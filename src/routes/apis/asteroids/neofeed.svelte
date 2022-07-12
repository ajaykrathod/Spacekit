<script context="module">
    export async function load({fetch}) {
        const res = await fetch(`https://api.nasa.gov/neo/rest/v1/feed?start_date=2015-09-07&end_date=2015-09-08&api_key=${import.meta.env.VITE_NASA_API_KEY}`)
        const neofeed = await res.json()
        if(res.ok){
            return{
                props : {
                    neofeed
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

    export let neofeed

    console.log(neofeed);
</script>
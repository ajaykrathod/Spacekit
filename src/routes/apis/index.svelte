<script>
// @ts-nocheck

let APIS = [
    {
        name:"APOD",
        link:'/',
        subtitle:"Astronomy Picture Of The Day",
        description : "One of the most popular websites at NASA is the Astronomy Picture of the Day. This endpoint structures the APOD imagery and associated metadata so that it can be repurposed for other applications."
    },
    {
        name:"EARTH",
        link:'/earth',
        subtitle:"Unlock the significant public investment in earth observation data",
        description : "Landsat imagery is provided to the public as a joint project between NASA and USGS. A recent industry report on landsat satellite imagery data estimates that total annual value to the economy of $2.19 billion, far exceeding the multi-year total cost of building, launching, and managing Landsat satellites and sensors. The value is derived from consumers use of the data. The objective of this endpoint is to give  an easy to use taste of what Landsat imagery data can provide. There are more complicated APIs available if  want to build models on top of satellite imagery, apply machine-learning, or minimize clouds in image. NASA's Earth Science Devision has a variety of Earth imagery APIs for developers, which can find out about in the Earthdata Developer Portal. Specifically, the GIBS (Global Imagery Browse Services) API may be of interest. The Google Earth Engine API is another powerful option. This API is powered by Google Earth Engine API, and currently only supports pan-sharpened Landsat 8 imagery."
    },
    {
        name:"EPIC",
        link:'/epic',
        subtitle:"Earth Poluchromatic Imaging Camera",
        description : "OThe EPIC API provides information on the daily imagery collected by DSCOVR's Earth Polychromatic Imaging Camera (EPIC) instrument. Uniquely positioned at the Earth-Sun Lagrange point, EPIC provides full disc imagery of the Earth and captures unique perspectives of certain astronomical events such as lunar transits using a 2048x2048 pixel CCD (Charge Coupled Device) detector coupled to a 30-cm aperture Cassegrain telescope."+
        "Image metadata and key information are provided by the JSON API and can be requested by date and for the most recent available date. A listing of all available dates can also be retrieved via the API for more granular control."
    },
    {
        name:"MARS Rover Photos",
        link:'/mars-rover',
        subtitle:"Image data gathered by NASA's Curiosity, Opportunity and Spirit rovers on Mars",
        description : "This API is designed to collect image data gathered by NASA's Curiosity, Opportunity, and Spirit rovers on Mars and make it more easily available to other developers, educators, and citizen scientists. This API is maintained by Chris Cerami."
        +"Each rover has its own set of photos stored in the database, which can be queried separately. There are several possible queries that can be made against the API. Photos are organized by the sol (Martian rotation or day) on which they were taken, counting up from the rover's landing date. A photo taken on Curiosity's 1000th Martian sol exploring Mars, for example, will have a sol attribute of 1000. If instead you prefer to search by the Earth date on which a photo was taken, you can do that, too."
        +"Along with querying by date, results can also be filtered by the camera with which it was taken and responses will be limited to 25 photos per call. Queries that should return more than 25 photos will be split onto several pages, which can be accessed by adding a 'page' param to the query."
    },
    {
        name:"NASA Image and Video Library",
        link:'/library',
        subtitle:"API to access the NASA Image nad Video Library site at images.nasa.gov",
        description : "Use this API to access the NASA Image and Video Library site at images.nasa.gov. For the latest documentation, please go here."
        +"The images.nasa.gov API is organized around REST, has predictable/resource­-oriented URLs and uses HTTP response codes to indicate API errors. This API uses built-­in HTTP features such as HTTP authentication and HTTP verbs, which are understood by many off-­the-­shelf HTTP clients. Please note that JSON is returned by all API responses, including errors. Each of the endpoints described below also contains example snippets which use the curl command­-line tool, Unix pipelines, and the python command­-line tool to output API responses in an easy­ to ­read format."
    },
]
</script>

<div class="container">
    {#each APIS as api}
        <div class="api">
            <a href={api.link}>
                <h1>{api.name}</h1>
            </a>
            <h2>{api.subtitle}</h2>
            <div class="description">{api.description}</div>
        </div>
    {/each}
</div>

<style>
    .container {
        position: relative;
        top: 8vh;
        display: flex;
        flex-direction: column;
    }
    a {
        text-decoration: none;
        color: black;
    }
    h2{
        margin-left: 4vw;
    }
    .api {
        margin: 2vh 3vw 0 3vw;
    }
    .description {
        margin: 2vh 2vw 0 6vw;
        text-align: center;
        font-size: larger;
    }
</style>
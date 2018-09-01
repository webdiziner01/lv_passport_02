<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card card-default">
                    <div class="card-header">Timeline</div>

                    <div class="card-body">




                        <ul class="list-unstyled">
                            <li class="media my-4" v-for="tweet in tweets">
                                <a href="#"><img class="mr-3"  src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEAAAABABAMAAABYR2ztAAAAIVBMVEXMzMyWlpbFxcWjo6O+vr63t7ecnJyqqqqbm5uxsbGampoKZyAaAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAU0lEQVRIiWNgGAWjYBQMd8Bk7KCITGMAZqeAQgZ2zwAwjQ2wmYU6ArVDaGyA0aWTkYHBFEpjM0FpoaABUzGExqaAJdmBkYFdNQBMj4JRMAoGOwAAPNIL2qWeApgAAAAASUVORK5CYII=" alt="" /></a>
                                <div class="media-body">
                                    <h5 class="mt-0 mb-1">{{tweet.user.name}}</h5>
                                    {{tweet.body}}
                                </div>
                            </li>
                        </ul>





                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
          return {
              tweets: []
          }
        },

        mounted() {
            //console.log('Component mounted.')
            // GET /someUrl
            axios
                .get('/tweets')
                .then((response) =>{
                    this.tweets = response.data

                })


        }
    }
</script>

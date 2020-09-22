<script>

let Robot = [
    {
        "name": "Jake",
        "color": "#bb4"
    },
    {
        "name": "Albert",
        "color": "red"
    },
    {
        "name": "Mike",
        "color": "green"
    },   
    {
        "name": "Jane",
        "color": "#992"
    },   
]
</script>

  <section class="cards">

        <div class="card">
            <h3 class="title" style="color:{Robot[0].color};">This is {Robot[0].name}</h3>
            <div id="mydiv"><img src="https://robohash.org/{Robot[0].name}" alt="img">
                <button class="btn btn-card">See more</button></div>
        </div>
        <div class="card">
            <h3 class="title" style="color:{Robot[1].color};">This is {Robot[1].name}</h3>
            <div id="mydiv"><img src="https://robohash.org/{Robot[1].name}" alt="img"> <button class="btn btn-card">See more</button>
            </div>

        </div>
        <div class="card">

            <h3 class="title" style="color:{Robot[2].color};">This is {Robot[2].name}</h3>


            <div id="mydiv"><img src="https://robohash.org/{Robot[2].name}" alt="img">
                <button class="btn btn-card">See more</button></div>
        </div>

        <div class="card">

            <h3 class="title" style="color:{Robot[3].color};">This is {Robot[3].name}</h3>
            <div id="mydiv"><img src="https://robohash.org/{Robot[3].name}" alt="img">
                <button class="btn btn-card">See more</button></div>
        </div>
    </section>

   <!--
   <section class="section-features">
        <div class="section-features__box">

        </div>

    </section> 
    -->


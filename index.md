
# Get Shredded.
<form id="getNumber">
    <label for="numEx">Desired Length of Workout (in minutes/exercises):</label>
    <input type="number" name="numEx" id="numEx">
    <br>

    <a href="#" onclick="advanced(this)">Show Advanced Options</a>
    <fieldset id="options" style="display: none;">
        <legend>Advanced Options</legend>
        
        <input type="checkbox" id="swiss" name="advancedOption" value="swiss">
        <label for="swiss">Swiss Ball Exercises</label>        

        <input type="checkbox" id="medball" name="advancedOption" value="medball">
        <label for="medball">Medicine Ball Exercises</label>

        <input type="checkbox" id="hips" name="advancedOption" value="hips" checked>
        <label for="medball">Hip Exercises</label>
    </fieldset>
</form>
<button onclick="getWorkout()">Get My Workout</button>

<p id="topworkoutlabel"></p>
<div id="workoutList"></div>

<script>
    function getWorkout(){
        let number = document.getElementById("numEx").value;
        document.getElementById("topworkoutlabel").innerHTML = "You've selected " + number + " exercises:";
        document.getElementById("workoutList").innerHTML = "";
        let EXERCISES = ["Elbow Plank",
        "Elbow Side Plank",
        "High Plank",
        "High Side Plank",
        "Back Plank",
        "High Plank with Arm Extensions",
        "Elbow Plank with Arm Extensions",
        "High Plank with Opposite Arm/Leg Extensions",
        "Elbow Plan with Opposite Arm/Leg Extensions",
        "Elbow Side Plank with Knee Drives",
        "High Side Plank with Knee Drives",
        "Elbow Side Plank with Top Leg Lifts",
        "High Side Plank with Top Leg Lifts",
        "Elbow Side Plank with Internal Rotation",
        "High Side Plank with Internal Rotation",
        "Pushups",
        "Wide Pushups",
        "Triangle Pushups",
        "Spiderman Pushups",
        "V Ups",
        "Russian Twists",
        "Toe Taps (Penguin Slides)",
        "Boats",
        "Accordions",
        "Supermans",
        "Leg Lifts",
        "Flutters",
        "Scissors",
        "Hip Extension Holds",
        "Hip Extension Leg Alternations",
        "Opposite Elbow to Knee Hold, other leg extended",
        "Mountain Climbers",
        "Swiss Ball Pikes",
        "Swiss Ball Side Tucks",
        "Swiss Ball Single Leg Drives",
        "Swiss Ball Stir the Pot",
        "Swiss Ball Glute Bridge Leg Extensions (shoulders on ball)",
        "Swiss Ball Hip Extensions",
        "Swiss Ball Rollouts",
        "Medicine Ball Pushups",
        "Medicine Ball Russian Twists",
        "Medicine Ball Pushups",
        "Fire Hydrants",
        "Donkey Kicks",
        "Side Lying Hip Abbduction",
        "Side Lying Hip Adduction",
        "Bird Dogs"
        ];

        if (number > EXERCISES.length) {
            number = EXERCISES.length;
        }
        for (var i = 0; i < number; i ++){
            let index = Math.floor(Math.random()*EXERCISES.length);
            document.getElementById("workoutList").innerHTML = document.getElementById("workoutList").innerHTML + String((i+1)) + ". " + EXERCISES.splice(index, 1)[0] + "<br>";
        }

    }

    function advanced(obj) {
        var content = document.getElementById("options");

        if (content.style.display == "none") {
            content.style.display = "";
            obj.innerHTML = "Hide Advanced Options";
        } else {
            content.style.display = "none";
            obj.innerHTML = "Show Advanced Options";
        }
    }
</script>

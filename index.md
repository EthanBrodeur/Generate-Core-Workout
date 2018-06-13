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
        let swiss = (document.getElementById("swiss").checked == true);
        let medball = (document.getElementById("medball").checked == true);
        let hips = (document.getElementById("hips").checked == true);

        document.getElementById("topworkoutlabel").innerHTML = "You've selected " + number + " exercises:";
        document.getElementById("workoutList").innerHTML = "";
        let EXERCISES = [
        ["Elbow Plank"],
        ["Elbow Side Plank"],
        ["High Plank"],
        ["High Side Plank"],
        ["Back Plank"],
        ["High Plank with Arm Extensions"],
        ["Elbow Plank with Arm Extensions"],
        ["High Plank with Opposite Arm/Leg Extensions"],
        ["Elbow Plan with Opposite Arm/Leg Extensions"],
        ["Elbow Side Plank with Knee Drives"],
        ["High Side Plank with Knee Drives"],
        ["Elbow Side Plank with Top Leg Lifts"],
        ["High Side Plank with Top Leg Lifts"],
        ["Elbow Side Plank with Internal Rotation"],
        ["High Side Plank with Internal Rotation"],
        ["Pushups"],
        ["Wide Pushups"],
        ["Triangle Pushups"],
        ["Spiderman Pushups"],
        ["V Ups"],
        ["Russian Twists"],
        ["Toe Taps (Penguin Slides)"],
        ["Boats"],
        ["Accordions"],
        ["Supermans"],
        ["Leg Lifts"],
        ["Flutters"],
        ["Scissors"],
        ["Hip Extension Holds"],
        ["Hip Extension Leg Alternations"],
        ["Opposite Elbow to Knee Hold, other leg extended"],
        ["Mountain Climbers"],
        ["Swiss Ball Pikes", "swiss"],
        ["Swiss Ball Side Tucks", "swiss"],
        ["Swiss Ball Single Leg Drives", "swiss"],
        ["Swiss Ball Stir the Pot", "swiss"],
        ["Swiss Ball Glute Bridge Leg Extensions (shoulders on ball)", "swiss"],
        ["Swiss Ball Hip Extensions", "swiss"],
        ["Swiss Ball Rollouts", "swiss"],
        ["Medicine Ball Pushups", "medball"],
        ["Medicine Ball Russian Twists", "medball"],
        ["Medicine Ball Pushups", "medball"],
        ["Fire Hydrants", "hips"],
        ["Clockwise Fire Hydrants", "hips"],
        ["Counterclockwise Fire Hydrants", "hips"],
        ["Donkey Kicks", "hips"],
        ["Side Lying Hip Abbduction", "hips"],
        ["Side Lying Hip Adduction", "hips"],
        ["Bird Dogs", "hips"],
        ];

        if (number > EXERCISES.length) {
            number = EXERCISES.length;
            alert("You picked more exercises than we've got! We'll give you " + EXERCISES.length + " exercises instead.");
        }
        for (var i = 0; i < number; i ++){
            var criteriaMet = false;
            let index = 0;
            while (!(criteriaMet)) {
                index = Math.floor(Math.random()*EXERCISES.length);
                if (swiss) {
                    if (!(EXERCISES[index].indexOf("swiss") > -1)) {
                        index = Math.floor(Math.random()*EXERCISES.length);
                        continue;
                    }
                }
                if (medball) {
                    if (!(EXERCISES[index].indexOf("medball") > -1)) {
                        index = Math.floor(Math.random()*EXERCISES.length);
                        continue;
                    }
                }
                if (hips) {
                    if (!(EXERCISES[index].indexOf("hips") > -1)) {
                        index = Math.floor(Math.random()*EXERCISES.length);
                        continue;
                    }
                }
                criteriaMet = true;
            }

            document.getElementById("workoutList").innerHTML = document.getElementById("workoutList").innerHTML + String((i+1)) + ". " + EXERCISES.splice(index, 1)[0][0] + "<br>";
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

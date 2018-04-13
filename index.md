
# Get Shredded.
<form id="getNumber">
    <label for="numEx">Desired Length of Workout (in minutes/exercises):</label>
    <input type="number" name="numEx" id="numEx"><br>
</form>
<button onclick="getWorkout()">Get My Workout</button>

<p id="topworkoutlabel"></p>
<div id="workoutList"></div>

<script>
    function getWorkout(){
        let number = document.getElementById("numEx").value;
        document.getElementById("topworkoutlabel").innerHTML = "You've selected " + number + " exercises:";
        
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
            document.getElementById("workoutList").innerHTML = document.getElementById("workoutList").innerHTML + EXERCISES.splice(index, 1)[0] + "\n";
        }

    }
</script>


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

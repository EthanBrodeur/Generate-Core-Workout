
# Get Shredded.
<form id="getNumber">
    <label for="numEx">Desired Length of Workout (in minutes/exercises):</label>
    <input type="number" name="numEx" id="numEx"><br>
</form>
<button onclick="getWorkout()">Get My Workout</button>

<p id="returntxt"></p>

<script>
    function getWorkout(){
        let number = document.getElementById("numEx");
        document.getElementById("returntxt").value = number
        alert(number) 
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

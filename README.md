<input id="question" placeholder="Ask something">
<button onclick="ask()">Ask</button>

<p id="answer"></p>

<script>
async function ask() {

let q = document.getElementById("question").value;

let response = await fetch("https://abc123.ngrok.io/ask", {
method: "POST",
headers: {
"Content-Type": "application/json"
},
body: JSON.stringify({question: q})
});

let data = await response.json();

document.getElementById("answer").innerText = data.answer;

}
</script>

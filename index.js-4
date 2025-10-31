const express = require("express");
const bodyParser = require("body-parser");
const path = require("path");

const app = express();

// Middleware
app.use(bodyParser.urlencoded({ extended: true }));
app.set("view engine", "ejs");
app.use(express.static(path.join(__dirname, "public")));

const port = process.env.PORT || 8080;

// Routes
app.get("/", (req, res) => {
  res.render("form", { result: "" });
});

app.post("/submit", (req, res) => {
  const reg = req.body.rno;
  const list = ["1", "2", "3" , "12"]; // Sample registered roll numbers

  if (list.includes(reg)) {
    res.render("form", { result: "PASS ✅" });
  } else {
    res.render("form", { result: "FAIL ❌" });
  }
});

app.get("/about", (req, res) => {
  res.send(
    "<h2>About Page</h2><p>This is a simple student result checker demo.</p>"
  );
});

app.listen(port, () => {
  console.log(`Listening on http://localhost:${port}`);
});

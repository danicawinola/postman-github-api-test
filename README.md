GitHub Issues API – Postman Practice

This is a small project where I used Postman to create GitHub Issues using the GitHub REST API.

The goal was to practice:

Sending API requests

Using Bearer Token authentication

Creating issues through API

Writing basic Postman tests

Exporting and uploading a Postman collection to GitHub

🚀 What This Project Does

Using Postman, I sent a POST request to:

https://api.github.com/repos/<my-username>/<repo-name>/issues


This automatically creates a new issue (task) in the GitHub repository.

🔑 Authentication (Bearer Token)

To authenticate, I created a Personal Access Token (classic) in GitHub with:

repo permission

Then in Postman:

Authorization → Bearer Token → paste the token

📝 Request Body (JSON)

This is the JSON used to create a new issue:

{
  "title": "My first issue",
  "body": "Created using Postman API"
}

🧪 Postman Tests

I added a few simple tests:

pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Issue title is correct", function () {
    let json = pm.response.json();
    pm.expect(json.title).to.eql("My first issue");
});


These tests confirm:

The issue was created successfully

The title in the response matches what I sent

📦 Files Included

Postman Collection (.json file)
Exported from Postman and uploaded to this repo.

🎯 What I Learned

How to use APIs with Postman

How GitHub issues can be created programmatically

How to use Bearer Token authentication

How to add basic Postman test scripts

How to organize an API practice project inside GitHub

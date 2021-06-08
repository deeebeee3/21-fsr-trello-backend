This backend will allow you to store and retrieve the application state.

We’ll use a naive approach and will send the whole state every time it changes.

---

To launch it go to code/01-first-app/trello-backend, install dependencies using
yarn and run yarn start:

yarn && yarn start

You should see this message:

Kanban backend running on http://localhost:4000!

You can verify that the backend works correctly by manually sending cURL requests. There are two endpoints available, one for storing data and one for retrieving.

---

Here is the command to store the data:

curl --header "Content-Type: application/json" --request POST --data '{"lists":"[]"}' http://localhost:4000/save

---

And here is the one to retrieve:

curl http://localhost:4000/load

---

Every time you POST a JSON object to the /save endpoint, the backend stores it in memory. Next time you call the /load endpoint, the backend sends the saved value back.

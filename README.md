# RESTing
This is a REST API backend for handling messages, users, communities, and channels — kind of like a minimal Slack clone. Everything’s in Python. Mostly focused on getting the DB interactions and endpoints working cleanly.

What it covers

Users can register and be suspended
You can create communities and channels
Direct messages and channel messages (with threading)
Reactions on messages
Simple message search
Test data and CI set up
How it’s structured

Everything lives in src/api. It’s broken down by endpoint, so you’ll see files like user_registration.py, message_creation.py, channel_detail.py, etc. There’s a db/ folder too for DB stuff, and server.py is the entry point.

Tests are in /tests. There's a CI config for GitLab too.

Running it

Install dependencies:

pip install -r requirements.txt
Run tests:

python3 -m unittest discover tests/
Start the server (roughly):

python3 src/server.py
Sample endpoints (rough idea)

POST /users/register
POST /communities
GET /channels/:id/messages
POST /messages
GET /messages/search?q=text
POST /messages/:id/react
Notes

Focus is on backend functionality, not frontend.
Designed to be testable, so there are a bunch of seed tests.
Username changes are limited (once every 6 months).
Suspensions are tracked and respected in API calls.

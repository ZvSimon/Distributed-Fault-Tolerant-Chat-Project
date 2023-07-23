
# P2P Distributed Messaging

This is a simple peer-to-peer distributed messaging system implemented in the python. The application has 2 systems. The first is an authentication server that helps the p2p nodes signup, signin and find bootstrap nodes. The second is the implementation of nodes that host methods for authentication through the auth server as well as messaging in a group chat and personal messaging.




## Features

- Users can authenticate: Users and sign up with a username and password and existing users can sign in to access more features.
- Broadcast Messaging: Users can send messages to all of its connected peers.
- Private Messaging: Users can send messages to specific users using their node ids.
- Vector Clocks: Each node maintains vector clocks against each message sent and received. They are maintained to maintain ordering of messages.
- Fetch Requests: Periodically, existing nodes ping the auth server for any pending connection requests. And if they receive one. They forward their connection history to that new node hence acting like a bootstrap node.




## Installation

1.	Clone the repository to your local system : 
```bash
  git clone <repo link>
```
 2.	Navigate to project directory:
```bash
  cd dir
```
    
## Usage/Examples
Auth : 
```python
from userinput import UserInput
user_input = UserInput("127.0.0.1", 8000, "127.0.0.1", 5000)
user_input.start_node()
user_input.signup("username", "password")
user_input.signin("username", "password")
Send Private Message:
user_input.send_private_message(recipient_node_id, "Hi there!")
Send Broadcast Message:
user_input.send_broadcast("Hello, everyone!")

```


## Acknowledgements

 This project was inspired by the need for a simple and efficient peer-to-peer group chat application using Python.


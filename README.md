# DistributedDJ
### Prerequisites (Mac OS X):
```
brew install mpg123
brew install portaudio
```
## Quick Demo:
``go run client.go clientconfig.json``

``Open new terminal window``

``go run terminal.go terminal_config.json``

## Introduction:
DistributedDJ is a distributed web radio that uses a peer-to-peer network where clients provide and stream songs that they locally own. Clients share the metadata of the songs they are willing to stream and are capable of voting amongst themselves to decide on the next song to play. The client with the selected song will become the host and stream the song to all the clients in the network. Playback of music is synchronized like traditional radio. Clients can join and and leave the network. They form a complete graph.

![alt text](https://user-images.githubusercontent.com/14913591/75271770-980c6b00-57b1-11ea-8474-06acfc80be01.png)

## Terminal
User interacts through the terminal node on their local machine. The terminal node first connects to a client on Azure to upload all the songs from user’s local machine. If the song’s name already exist in the network, meaning another user already uploaded the same song, then this song won’t be uploaded. The client receives songs and cache them to disk.
A user can interact with a terminal through the following commands:
1. show: requests a list of available songs for streaming
2. start: start playing the stream
3. stop: stop the stream locally
4. [song name]: user can vote by typing the song name when prompt to vote
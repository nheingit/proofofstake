Alrighty yall, This is just a quick chain I tossed together. I want to add persistence to this, but that will come a bit later.

For now you can make a .env file, and in there put in: `PORT=9000`

Get yourself setup with the `go mod` system so that is properly running in your project.

Next you should be able to execute the command: `go run main.go`

This will startup a node, and then you can connect other validators that will have a balance and a BPM. This BPM is arbitrary and just represents any data we would plug in to a block.

Open up a new terminal window and run: `nc localhost 9000`

It should ask you what your balances is, and what your BPM is.

Repeat that process 2-3 more times so that we have multiple validators all with different (or the same I'm not your mom to tell you what to do) balances. You should see a winner selected every 30 seconds and then all of the terminals will get a broadcast message, this will repeat so long as the main terminal that you ran `go run main.go` from is running.

I cobbled this together from another Proof of Stake tutorial, and I don't really like how the blocks are architected. I will also need to make this a bit lower level and convert many of the strings into bytes to keep everything a bit quicker, and for easier read/write access to the BadgerDB that I'm going to implement.

Python code that demonstrates fountain codes.

### License
If you really want to use any of the software in this repository, it is
licenced under the MIT license, as given in LICENSE.

### Usage
The scripts can be used to send a file through UDP using LT fountain codes to
ensure that the file will eventually be fully received.  In these instructions,
server is the computer that is going to send the file and client is the computer
that is going to receive the file.  <address> is the address of the server,
<filename> is the name of the file to send, and <filelength> is the length in
bytes of the file to send.

On the server run the command
`python3 udp.py -s -H <address> <filename>`
Then, on the client run the command
`python3 udp.py -H <address> -l <filelength> <filename>`

Even after the client has received the file, the server will still be sending
droplets to the client, so you'll need to terminate the script manually.

### Known issues
A recursion depth runtime error can occur when this script is run, but due to
the random nature of the LT algorithm, this should not occur on a consistent
basis.

# Intro

A P2P example made with Java DatagramSocket.

## How it works?

It uses a third party to tell peers what their public IP and port is(which is used for send message to the Server), then the peers will try to connect to each other.

And this technique is so called 'hole punching'.

It's not 100% works, depends on the NAT types.

# How to build?

Use gradle wrapper to build executable Jar file, then the `Peer.jar` and the `Server.jar` will be located at directory `./build/jar`

```
./gradlew build
```

or if you're using Windows

```
gradlew.bat build
```

(Actually, I'm not sure about this, cause my laptop is running Linux :D. I like Linux, BTW.)

## Lazy to build?

You can download Jars from [here](https://github.com/yanzhen0610/p2p-java/releases)

# Run

## Peer

Run with command.

```
java -jar Peer.jar <Server>[:port] [group_id]
```

The default `group_id` is `default`.

### Example

If the server address is `hello.noip.me`.

```
java -jar Peer.jar hello.noip.me
```

## Server

The default listening port is `5555`.

```
java -jar Server.jar [listening_port]
```

### Example

```
java -jar Server.jar
```

# How to know is it works?

If other peers join the same group

```
1.2.3.4:56789 joined
```

otherwise

```
1.2.3.4:56789 left
```

If successfully message from other peers, it'll output something like

```
1.2.3.4:56789 'Hi! I'm musing_lalande'
```

# kafka-streams-pitfalls (aka my Streams application does not publish anything)

You know Kafka is cool. Kafka streams are cooler; but this doesn't mean streams applications get written automagically.
Like any software you have to take care of some stuff.



## Pitfall #1 : Use the right POM

## Pitfall #2: Use the Zookeeper (at least until Kafka 0.12.+)

## Pitfall #3: Beware of topic names

## Pitfall #4: KStream.print() is your friend

Are you (really) sure your streams code is doing something with the data.
Maybe you are 

## Pitfall #5: Use the wallclock timer.

## Pitfall #6: Do you have a key, bro?

My streams code does not publish anything.
Pro
Before trying anything else,
Try this *very* minimal stream echo code:

```{java}

// If you cannot produce Kafka messages with this "Streams echo server"
// 

final KStreamBuilder builder = new KStreamBuilder();
KStream inStream  = builder.stream("TOPIC-with-an-obscene-amount-of-messages");
KStream <String,String> streamCounter =  inStream ;
streamCounter.to("TOPIC-where-I-cannot-write");
streamCounter.print();

```


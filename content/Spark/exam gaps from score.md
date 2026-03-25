# exam gaps from what i learnt

what to focus next (short and practical)

## 1) spark connect (main gap)
my current understanding:
client and server split, gRPC communication.

what i still need to explore:
- what is supported vs not supported compared to classic session
- version compatibility traps
- remote path/config confusion
- deployment auth/network basics

practice:
- make one tiny spark connect app
- write 1 failure + fix here

## 2) structured streaming (second gap)
i know output mode + watermark basics already.

need deeper confidence in:
- trigger choices and tradeoffs
- checkpoint behavior and recovery
- stream-stream join behavior
- state growth and late data tuning

practice:
- run one end-to-end stream with checkpoint
- test late data by changing watermark window

## 3) spark sql (third gap)
i use dataframe api a lot, sql depth needs polish.

focus:
- explain plan reading habit
- join strategy selection (broadcast vs shuffle)
- null behavior edge cases
- cte readability for complex transformations

practice:
- solve 3 queries, then inspect explain for each


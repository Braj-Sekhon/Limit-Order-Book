# Orderbook Engine

Has two main datastructures

## The Matching Orderbook

- Holds price buckets
- - Records an order queue
- - Records the amount held in a queue
- Best bid and best ask

## The Ledger

- Records all trade IDs
- - Buys
- - Sells

## Mechanics

Cancelled Orders:

- Mark the trade ID as dirty/cancelled in the Ledger and reduce the price bucket count
- The trade is not removed immediately from the price bucket count
- When a trade is executed and is walking down the order queue, check each trade's ID in the ledger to see if it's dirty/cancelled

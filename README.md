# Await/async experiments

This is a small set of experiments / explorations into the await/async feature described in PEP-0492 (https://www.python.org/dev/peps/pep-0492/) and implemented in Python 3.5.


## Experiment 1 - Simplest scheduler.

The goal of experiment 1 is to have a essentially the simplest possible co-routine scheduler.
This is in juxtaposition to the relatively complex schedulers found in the standard asyncio module.

## Experiement 2 - Simple scheduler w/ sleep function

The goal of experiment 2 is to add an awaitable sleep co-routine function to our scheduler.
This adds a reasonable amount of complexity to the scheduler, although the sleep function itself is rather simple.
Whether or not this sleep aspect of the scheduler will be easily composable with other events in the future will be interesting.

## Experiment 3 - Enable adding new co-routines

Currently only the co-routines specified at the start can be scheduled.
The goal of this experiment is to allow new co-routines to be added after the scheudler has started running.

## Experiment 4 - Interacting with a thread pool

Sometimes there are compute (or IO) task that would be better to perform in the background, not on the main thread.
This experiment shows an example of the ThreadPoolExecuter interacting with scheduled co-routines to achieve backgrounded computation.
This technique probably won't be a good basis in the long run as it will not be possible to wait on an IO selector and a thread Queue at the same time.

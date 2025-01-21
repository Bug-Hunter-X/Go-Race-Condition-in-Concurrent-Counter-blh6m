# Go Race Condition in Concurrent Counter

This repository demonstrates a common race condition bug in Go. The program attempts to increment a counter from multiple goroutines without using proper synchronization primitives. This can lead to incorrect results where the final counter value is less than expected.

## Bug Description

The `bug.go` file contains a program that launches 1000 goroutines, each incrementing a shared counter variable.  Due to the lack of synchronization, the increments may not be atomic, resulting in a final counter value lower than 1000.

## Solution

The `bugSolution.go` file provides a corrected version of the program that uses a mutex to protect the counter variable from race conditions. This ensures that only one goroutine can access and modify the counter at any given time, resulting in the correct final count.

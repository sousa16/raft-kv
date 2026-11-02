# raft-kv

A replicated key-value store written in Go on the Raft consensus algorithm, with a gRPC API. I am building it to learn Go and distributed systems.

**Status: in progress.** Nothing is implemented yet; the repo currently holds only this README. The plan below gets ticked off as each part lands.

## Plan

- [ ] Design doc, repo with CI, single-node store with a gRPC API and a write-ahead log
- [ ] Leader election, tested on a simulated network with a fake clock
- [ ] Log replication and commit
- [ ] Persistence and crash recovery
- [ ] Snapshots, log compaction and client request deduplication
- [ ] 5-node Docker Compose cluster, fault injection (network partitions, node kills), metrics and benchmarks

## Approach

- Tests run with Go's race detector (`go test -race`).
- Consensus logic is tested against a simulated network and a fake clock, so failures can be reproduced.
- Each milestone is tagged, and this README is updated with it.

## References

- [In Search of an Understandable Consensus Algorithm](https://raft.github.io/raft.pdf) (Ongaro and Ousterhout), the Raft paper
- [The Raft visualization](https://raft.github.io/)

# PES Version Control System (PES-VCS)

## Author

Prachi Joshi
SRN: PES1UG24CS325

---

## Objective

This project implements a simplified Git-like version control system.
It demonstrates content-addressable storage, tree structures, staging, and commit history.

---

## Platform

Ubuntu 22.04

---

## Build Instructions

```
make
make all
make clean
```

---

# Phase 1: Object Storage

### Description

Implemented SHA-256 based content-addressable storage with directory sharding.

### Output

<img width="751" height="215" alt="osoran1a" src="https://github.com/user-attachments/assets/d3d208ab-25e5-4d27-ace8-639f95e0dbb2" />


### Object Storage

<img width="747" height="152" alt="osoran1b" src="https://github.com/user-attachments/assets/4b3aae76-648e-4528-8035-0ff1637b0db3" />


---

# Phase 2: Tree Objects

### Description

Implemented tree construction and deterministic serialization.

### Output

<img width="615" height="129" alt="osoran2" src="https://github.com/user-attachments/assets/6b3bef2e-cc2a-4b61-a202-eb06f60bef78" />


---

# Phase 3: Index (Staging Area)

### Description

Implemented staging system using a text-based index file.

### Status Output and Index file

<img width="749" height="638" alt="ororan3" src="https://github.com/user-attachments/assets/f39dd5a0-5d1e-4f90-b978-d0548a45f919" />


---

# Phase 4: Commits

### Description

Implemented commit creation linking tree snapshots and metadata.

### Commit Output

<img width="749" height="133" alt="osoran4" src="https://github.com/user-attachments/assets/51d8a7b4-34e1-4b26-907b-cb8b9d912be1" />


---

# Implementation Files

* object.c — object storage
* tree.c — tree construction
* index.c — staging area
* commit.c — commit creation

---

# Analysis Questions

## Q5.1 Branch Checkout

Checkout updates HEAD and working directory to match the branch. It modifies reference files and replaces working directory contents.

## Q5.2 Dirty Working Directory

Compare working directory metadata with index entries. If mismatched, block checkout.

## Q5.3 Detached HEAD

HEAD points to a commit directly. New commits are not part of a branch but can be recovered using commit hashes.

---

## Q6.1 Garbage Collection

Traverse from all references, mark reachable objects, and delete unreachable ones.

## Q6.2 GC Race Condition

Concurrent GC may delete objects being written. Git prevents this using locking mechanisms.

---

# Commit Requirement

Each phase contains at least 5 commits demonstrating incremental progress.

---

# Conclusion

This project demonstrates the internal working of Git including object storage, trees, indexing, and commit history.

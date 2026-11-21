---
name: secure-aggregation-and-compute
domain: software-engineering/secure-aggregation-and-compute
trigger: "Protecting model updates or inputs in transit with cryptography."
anti_trigger: "Not for DP accounting, and not for the federated optimization."
scope: "Secure aggregation, homomorphic encryption, MPC."
status: seedling
---

# Secure aggregation and compute

## Standard

Federation moves the privacy problem rather than solving it: the server still receives each client's update, and an update is itself a leaky object that can be inverted to recover training examples. Secure aggregation closes that hole by ensuring the server learns only the sum of the clients' updates, never any individual one. The Bonawitz protocol achieves this with pairwise masking: clients agree on shared random masks that cancel exactly when the masked updates are summed, so the aggregate is correct while each contribution stays hidden, and the protocol tolerates a fraction of clients dropping out mid-round.

Cryptographic computation generalises the idea. Homomorphic encryption lets a server compute on ciphertexts so that the decrypted result matches the computation on the plaintext; partially homomorphic schemes support one operation cheaply, while fully homomorphic encryption supports arbitrary computation at a large cost. Secure multi-party computation splits a computation across parties so none learns the others' inputs. Each of these buys confidentiality of the input or update in transit, at a real overhead in computation and communication, and none of them bounds what the final model reveals — that remains differential privacy's job.

Primary sources: <https://arxiv.org/abs/1611.04482> and <https://en.wikipedia.org/wiki/Homomorphic_encryption>.

## Decision rules

- Use secure aggregation when the server must not see individual updates, only their sum.
- Choose a dropout-tolerant protocol; real federated rounds lose clients.
- Distinguish partial from full homomorphic encryption; the cost difference is enormous.
- Reach for MPC when several parties must jointly compute without revealing inputs.
- Budget the computation and communication overhead before committing to a scheme.
- Remember the boundary: these protect data in transit, not what the released model leaks.

## Procedure

1. Identify what must be hidden: individual updates, inputs, or intermediate results.
2. Select secure aggregation for sums, homomorphic encryption for server-side compute, or MPC for joint compute.
3. Instantiate the masking or key-agreement step with dropout tolerance.
4. Measure the added computation and communication against the non-cryptographic baseline.
5. Verify the aggregate or decrypted result matches the plaintext computation.
6. Record the scheme, its overhead, and the residual leakage it does not address.

## Anti-patterns

- Treating secure aggregation as a substitute for differential privacy on the final model.
- A protocol that aborts the whole round when one client drops.
- Assuming fully homomorphic encryption is cheap enough to use everywhere.
- Verifying only correctness and ignoring the communication blow-up.
- Claiming end-to-end privacy while the released model can be interrogated.

## Done checklist

- [ ] Hidden object named (updates, inputs, intermediates).
- [ ] Scheme matched to the object and the operation.
- [ ] Dropout tolerance configured.
- [ ] Overhead measured against baseline.
- [ ] Correctness against plaintext verified.
- [ ] Residual model-leakage risk recorded.

## Sources

- Practical Secure Aggregation for Federated Learning (Bonawitz et al.): <https://arxiv.org/abs/1611.04482>
- Homomorphic encryption overview: <https://en.wikipedia.org/wiki/Homomorphic_encryption>
- Secure multi-party computation overview: <https://en.wikipedia.org/wiki/Secure_multi-party_computation>
- OpenMined PySyft, privacy-preserving ML tooling: <https://github.com/OpenMined/PySyft>

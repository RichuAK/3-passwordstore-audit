### [H-1] Storing the password on-chain makes it visible to anyone, and no longer private.

**Description:** All data stored on-chain is visible to anyone, and can be read directly from the blockchain. The `PasswordStore::s_password` variable is intended to be a private variable and only accessed through the `PasswordStore::getPassword` function, which is intended to be only called by the owner of the contract.

**Impact:** Anyone can read the private password, severely breaking the functionality of the protocol.

**Proof of Concept:** `cast storage` or `vm.load`

**Recommended Mitigation:** Store the password offchain. AKA, defeats the purpose of this contract.

# ZK-SNARK proof verification in Plutus

A Plutus implementation of the Groth16 ZKP-verification algorithm.

Tested a zk-SNARK using a basic implementation of Miller's algorithm and the _toy_ elliptic curve BLS6_6.

## Testing instructions

We assume that you have cloned [Plutus-Apps](https://github.com/input-output-hk/plutus-apps) and have [Nix](https://nixos.org/) installed and configured with the proper [substituters](https://github.com/input-output-hk/plutus-apps/tree/v1.0.0#iohk-binary-cache).  At the `Plutus-Apps` directory, execute

```shell
git checkout v1.0.0
nix-shell
```

After allowing enough time for the nix-shell to start, execute

```shell
cabal repl
```

The REPL should open in module `Test_BLS6_6`.


### ZK-proof verification using the BLS6_6</sub> elliptic curve

Inside the REPL, execute:

```shell
testValidator1
```


## Files

Directory `src/BLS6_6` provides:

-   `Params_BLS6_6` :  global parameters associated with elliptic curve **BLS6_6</sub>**.
-   `ZKPPVerification_BLS6_6` :  identical to `ZKPVerification.hs` except that imports BLS6_6</sub> parameters.
-   `Test_BLS6_6` :  allows convenient testing of the validator in the REPL.

## Notes

-   Elliptic curve `BLS6_6` is described in detail in [1].

-   Datum in file `Test_BLS6_6.hs` was obtained from the ZK-SNARK setup and proof associated with the *3-factorization problem* as explained in [1].


## Reference

[1]  [The MoonMath Manual to zk-SNARKs](https://leastauthority.com/community-matters/moonmath-manual/) .

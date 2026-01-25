# Ideas for leanXMSS

An interesting objective could be to prove:
- \> 128-bits (resp. \> 64 bits) of classical (resp. quantum), multi user, security in the ROM (resp. QROM)
- \> 100-bits (resp. \> TODO bits) of classical (resp. quantum), single user, security in the standard model

... when hash digest = 5 koala-bears (≈ 155 bits)

Advantages:
- shorter signatures, fitting in a single MTU (1500 bytes)
- enables to use a single "flavour" of Poseidon, over 16 field elements (no need for an additional permutation over 24 elements) -> simplicity

In the Merkle Tree (which is the bottleneck in terms of number of field elements to hash), we could use the following number of field elements:

[Public Param = 4][Tweak = 2][left_child = 5][right_child = 5] -> 16 field elements

(Random idea: if we want more than 124 bits (4 field elements) for the public parameter, we could use a field element at the same time for the public parameter (using around 2/3) and for the tweak (using around 1/3). Because the tweak only needs log2(L.w.v) = 32 + 3 + 6 = 41 bits = 1 field element + 10 bits, which would basically enable a public parameter of around 145 bits)


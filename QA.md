# Low Impact Issues

## 1 Launch Time Calculation Could Be Improved
The contract uses fixed periods such as 90 days and 360 days to calculate `titnOut` in the `quoteTitn` function. These hardcoded values may not be ideal, especially if the contract needs to be flexible in the future (e.g., different periods for different launch phases). Hardcoding periods could limit the contract’s adaptability.

**Instances (2):**

```solidity
File: ./contracts/MergeTgt.sol

11: contract MergeTgt is IMerge, Ownable, ReentrancyGuard {

```

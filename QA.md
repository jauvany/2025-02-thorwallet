# Low Impact Issues

## 1 Launch Time Calculation Could Be Improved
The contract uses fixed periods such as 90 days and 360 days to calculate `titnOut` in the `quoteTitn` function. These hardcoded values may not be ideal, especially if the contract needs to be flexible in the future (e.g., different periods for different launch phases). Hardcoding periods could limit the contract’s adaptability.

**Instances (8):**

```solidity
File: ./contracts/MergeTgt.sol

75:  if (block.timestamp - launchTime > 360 days) {

99:  if (block.timestamp - launchTime >= 360 days) {

117: if (block.timestamp - launchTime < 360 days) {

157: if (timeSinceLaunch < 90 days) {

159: } else if (timeSinceLaunch < 360 days) {

160: uint256 remainingtime = 360 days - timeSinceLaunch;

161: titnAmount = (tgtAmount * TITN_ARB * remainingtime) / (TGT_TO_EXCHANGE * 270 days); //270 days = 9 months

```
https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L75

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L99

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L117

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L157

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L159

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L160

https://github.com/jauvany/2025-02-thorwallet/blob/99c698cc9e468acef15d9e6d20e43ba4ac8e736c/contracts/MergeTgt.sol#L161

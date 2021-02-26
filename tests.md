```

  ClaimConfig
    ✓ Should throw if deploy with owner as dev
    ✓ Should deploy ClaimManagement (251ms)
    ✓ Should have correct default values on deploy (84ms)
    ✓ Should only allow governance to set new governance
    ✓ Should throw if set governance to owner
    ✓ Should throw if set governance to 0
    ✓ Should set new governance (43ms)
    ✓ Should only allow governance to set treasury
    ✓ Should throw if set treasury to 0
    ✓ Should set treasury
    ✓ Should only allow owner to set auditor
    ✓ Should set auditor (55ms)
    ✓ Should remove auditor (42ms)
    ✓ Should set fee multiplier (38ms)
    ✓ Should set fee and currency (68ms)

  ClaimManagement
    ✓ Should deploy ClaimManagement and set governance, auditor(set to 0x0), treasury, and factory (45ms)
    ✓ Should approve claim management for balance (47ms)
    ✓ Should set feeCurrency to dai
    ✓ Should not rely on auditor since address is set to 0x0
    ✓ Should set auditor
    ✓ Should throw if filing a claim for incident in the future
    ✓ Should throw if filing a claim for incident more than 14 days ago
    ✓ Should throw if filing a claim for 0 address
    ✓ Should throw if protocol name doesn't match address
    ✓ Should cost 10 dai to file claim
    ✓ Should file a normal claim (68ms)
    ✓ Should have correct claim values
    ✓ Should be mapped under nonce = 0
    ✓ Should deduct 10 dai from claim filer
    ✓ Should cost 20 dai to file next claim
    ✓ Should file another normal claim (49ms)
    ✓ Should deduct 20 dai from claim filer
    ✓ Should have both claims under filed
    ✓ Should throw when forceFileClaim if !isAuditorVoting (38ms)
    ✓ Should NOT allow force filing a claim for 0 address
    ✓ Should file a forced claim (45ms)
    ✓ Should deduct 500 dai from claim filer
    ✓ Should have correct force claim values
    ✓ Should have 530(10 + 20 + 500) dai in management contract
    ✓ Should throw if try to validate when !isAuditorVoting (42ms)
    ✓ Should throw if try to validate zero address
    ✓ Should throw if nonce != claimNonce()
    ✓ Should throw if index >= protocolClaims length
    ✓ Should not allow validating a forcedClaim
    ✓ Should invalidate claim
    ✓ Should be in invalidated state
    ✓ Should have a decidedTimestamp
    ✓ Should send feePaid (10) to treasury
    ✓ Should throw if trying to validate claim that is already validated
    ✓ Should throw if claim is not pending for validateClaim
    ✓ Should validate claim
    ✓ Should resetClaimFee to baseClaimFee when claim is validated
    ✓ Should file and validate more claims for further testing (113ms)
    ✓ Should throw if owner decideClaim when isAuditorVoting
    ✓ Should throw if auditor decideClaim when !isAuditorVoting (40ms)
    ✓ Should throw if deciding a claim for zero address
    ✓ Should throw if input nonce != protocol nonce
    ✓ Should throw if index >= length
    ✓ Should throw if claim is not pending for decideClaim
    ✓ Should throw if payoutNumerator != payoutDenominator when allowPartialClaim == false
    ✓ Should throw if payoutNumerator > payoutDenominator
    ✓ Should throw if payoutNumerator <= 0 when accepting
    ✓ Should accept claim (45ms)
    ✓ Should be in accepted state
    ✓ Should have payoutNumerator/payoutDenominator = 1
    ✓ Should have decidedTimestamp
    ✓ Should refund feePaid to first claim filer
    ✓ Should remove auditor
    ✓ Should file new claims under nonce = 1 (44ms)
    ✓ Should throw if owner tries to validateClaim when auditor is not voting
    ✓ Should throw if payoutNumerator != 0 when denying claim
    ✓ Should deny claim
    ✓ Should be in denied state
    ✓ Should have payoutNumerator = 0 and payoutDenominator = 1
    ✓ Should file 2 new claims (73ms)
    ✓ Should revert if try to validate claim with payoutNumerator > 0 after window passed
    ✓ Should deny claim if window passed and claimIsAccepted = false
    ✓ Should have correct claim values
    ✓ Should deny claim if window passed even if pass in true for claimIsAccepted

  Cover
    ✓ Should initialize correct state variables (126ms)
    ✓ Should match computed covToken addresses (58ms)
    ✓ Should set CovTokenSymbol by dev (52ms)
    ✓ Should NOT set CovTokenSymbol by non-dev
    ✓ Should redeem collateral without accepted claim (107ms)
    ✓ Should redeem collateral(0 fee) without accepted claim (141ms)
    ✓ Should NOT redeem collateral with accepted claim
    ✓ Should NOT redeem collateral after cover expired
    ✓ Should NOT redeemNoclaim before expire
    ✓ Should NOT redeemNoclaim after expire before wait period ends
    ✓ Should redeemNoclaim after expire and after wait period ends (93ms)
    ✓ Should NOT redeemNoclaim after expire if does not hold noclaim covToken
    ✓ Should NOT redeemClaim before accepted claim
    ✓ Should NOT redeemClaim after enact claim before redeemDelay ends (76ms)
    ✓ Should allow redeem partial claim and noclaim after enact 40% claim after claimRedeemDelay ends (210ms)
    ✓ Should allow redeem noclaim ONLY after enact and noclaimRedeemDelay if incident after expiration (142ms)
    ✓ Should NOT redeemClaim after enact if does not have claim token

  CoverERC20
    ✓ Should deploy with correct name, symbol, decimals, totalSupply, balanceOf
    ✓ Should mint tokens to userA and userB
    ✓ Should update totalSupply after mint
    ✓ Should NOT mint tokens signed by non-owner
    ✓ Should allow transfer from userA to userB
    ✓ Should approve
    ✓ Should transferFrom within allowance
    ✓ Should NOT transferFrom when amount > allowance
    ✓ Should NOT burn by non-owner
    ✓ Should burn userB balance by owner
    ✓ Should burn

  Protocol
    ✓ Should initialize correct state variables (69ms)
    ✓ Should update state variables by the correct authority (111ms)
    ✓ Should NOT update state variables by the wrong authority
    ✓ Should add cover for userA (127ms)
    ✓ Should match cover with computed cover address (131ms)
    ✓ Should create new cover contract for diffrent expiration timestamps (208ms)
    ✓ Should add cover for userB on existing contract (229ms)
    ✓ Should create new cover for userB on existing contract when accepted claim (222ms)
    ✓ Should emit event and enactClaim if called by claimManager (48ms)
    ✓ Should NOT enactClaim if protocol nonce not match (49ms)
    ✓ Should NOT enactClaim if called by non-claimManager
    ✓ Should NOT add cover for userA for expired timestamp

  ProtocolFactory
    ✓ Should deploy with correct state variable values
    ✓ Should emit ProtocolInitiation event
    ✓ Should NOT update governance to address(0) by governance
    ✓ Should NOT update governance to owner by governance
    ✓ Should only update fees correctly by governance (40ms)
    ✓ Should update claimManager by owner
    ✓ Should NOT update claimManager by non-owner
    ✓ Should add 2 new protocols by owner (89ms)
    ✓ Should compute the same protocol addresses (54ms)
    ✓ Should NOT add new protocol by userA


  129 passing (15s)
```

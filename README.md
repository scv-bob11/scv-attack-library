# scv-attack-library

|NUMBER|ATTACK VETCOR                                          |DESCRIPTION                                                                     |CWE-NUMBER|IMPACT|SOLIDITY-VERSION|
|------|-------------------------------------------------------|--------------------------------------------------------------------------------|----------|------|----------------|
|100   |Call or Delegatecall to Untrusted Callee               |Call 이나 Delegatecall을 신뢰할 수 없는 callee의 권한으로 실행 가능한 경우                           |829       |      |                |
|101   |Insufficient Gas Griefing                              |sub-call을 사용하고 해당 call이 실패했을 때 전달자는 트랜잭션을 검열이 가능하지만 sub-call을 성공시키기에는 가스가 부족한 경우|691       |      |                |
|102   |Arbitrary Jump with Function Type Variable             |어셈블리를 사용해서 function 변수를 지정하여 function-call을 사용하는 경우                             |695       |      |                |
|103   |Griefing bug                                           |저수준의 call로 악의적인 code를 실행하여 임의의 자산을 인질로 삼을 수 있는 경우                                |691       |      |                |
|104   |Arbitrary Call Data                                    |low level call을 사용할 때 call data의 검증이 부족한 경우                                     |223       |      |                |
|200   |Function Default Visibility                            |Visibilty를 명시하지 않아서 public으로 설정되는 보안약점                                          |710       |      |                |
|201   |Unchecked call Return Value                            |함수의 Return value를 검증하지 않아 발생하는 보안약점                                             |252       |      |                |
|202   |Unprotected SELFDESTRUCT Instruction                   |SELFDESTRUCT 명령어를 유효한 access control 없이 사용이 가능한 경우                                |284       |      |                |
|203   |Reentrancy                                             |외부 contract를 호출하는 경우 첫 번째 호출이 완료되기 전 호출 계약을 다시 호출하는 경우                          |841       |      |                |
|204   |State Variable Default Visibility                      |중요 변수의 visibility를 설정하지 않아 public으로 설정되는 경우                                     |710       |      |                |
|205   |Use of Deprecated Solidity function                    |더 이상 사용하지 않는 solidity 함수 사용                                                     |477       |      |                |
|206   |DOS with Failed call                                   |외부 호출이 실수 또는 의도적으로 실패하여 contract에 DOS가 가능한 경우                                   |703       |      |                |
|207   |Incorrect Constructor Name                             |잘못된 constructor 이름을 사용한 경우                                                      |665       |      |< 0.4.22        |
|208   |Missing Protection against Signature Replay Attacks    |서명의 replay attack에 대한 검증이 없는 경우                                                 |347       |      |                |
|209   |Requirement Violation                                  |Require구문이 미흡하거나, 불필요하게 강력해 요구 조건을 따르지 못하는 경우                                   |573       |      |                |
|210   |Incorrect Inheritance Order                            |상속 순서가 틀린 경우                                                                    |696       |      |                |
|211   |Unexpected Ether balance                               |Ether의 잔액을 엄격하게 가정했으나 예상하지 못한 잔액이 존재하는 경우                                       |667       |      |                |
|212   |Code With No Effects                                   |효과가 없는 코드가 존재                                                                   |1164      |      |                |
|213   |Lack of Proper parameter                               |매개 변수의 검증이 미흡한 경우                                                               |20        |      |                |
|214   |Unchecked External call                                |External call이 fail 되었는지 확인하지 않는 경우                                             |252       |      |                |
|215   |Assert Violation                                       |assert 구문이 항상 잘못된 경우                                                            |670       |      |                |
|216   |Incorrect Comparison                                   |잘못된 비교 사용                                                                       |697       |      |                |
|217   |Unexpected token balance                               |token의 잔액을 엄격하게 가정했으나 예상하지 못한 잔액이 존재하는 경우                                       |667       |      |                |
|218   |Short Address Attack                                   |주소는 20bytes이지만 contract에서 검증하지 않는 경우                                             |130       |      |                |
|219   |Incorrect Behavior Order                               |동작 순서가 잘못된 경우                                                                   |696       |      |                |
|220   |Improper Access Control                                |잘못된 접근 제어를 사용하는 경우                                                              |284       |      |                |
|221   |Unverified Ownership                                   |Onwer 확인 없이 사용하는 경우                                                             |283       |      |                |
|300   |DoS With Block Gas Limit                               |시간에 따라 무한히 증가하는 배열 등을 사용하여 실행 비용을 초과 시켜 DOS가 발생하는 경우                            |400       |      |                |
|301   |Message call with hardcoded gas amount                 |call을 실행하는 gas의 비용을 하드코딩한 경우                                                   |665       |      |                |
|400   |Uninitialized Storage Pointer                          |storage pointer를 초기화 하지 않아 다른 contract의 위치를 가르키는 경우                             |824       |      |< 0.5.0         |
|401   |Shadowing State Variables                              |contract 상속 시 변수의 모호성이 발생하는 경우                                                  |710       |      |                |
|402   |Write to Arbitrary Storage Location                    |임의의 storage에 write가 가능한 경우                                                      |123       |      |                |
|403   |Presence of unused variables                           |사용하지 않는 변수의 존재                                                                  |1164      |      |                |
|404   |Unencrypted Private Data On-Chain                      |On Chain에서 private 변수에 중요 정보를 저장하는 경우                                           |767       |      |                |
|405   |Uninitialized Variable                                 |중요 변수가 초기화 되어있지 않는 경우                                                           |457       |      |                |
|406   |Use Incorrect Type                                     |잘못된 type 사용                                                                     |          |      |                |
|407   |Incorrect Type Conversion or Cast                      |잘못된 type 변환 또는 casting                                                          |704       |      |                |
|408   |Reference to unupdated variable                        |업데이트되지 않은 변수 참조                                                                 |345       |      |                |
|409   |Resue of ID to be used once                            |1번만 사용되어야 할 ID의 재사용                                                             |285       |      |                |
|500   |Transaction Order Dependence                           |Transaction이 순서에 영향을 받는 경우 racecondition이 발생함                                   |362       |      |                |
|501   |Double spend                                           |동일한 UTXO가 여러 번 사용되어 이중 지출이 가능한 경우                                               |345       |      |                |
|502   |Front running                                          |state나 변수가 트랜젝션 삽입 순서에 영향을 받는 경우                                                |367       |      |                |
|503   |Block Timestamp Manipulation                           |채굴자가 blockTimestamp를 임의로 조작 할 경우 발생할 수 있는 취약점                                   |829       |      |                |
|600   |Signature Malleability                                 |악의적 사용자가 v, r, s 값으로 다른 유효한 signature를 생성 할 수 있는 경우                             |347       |      |                |
|601   |Lack of Proper Signature Verification                  |서명 검증이 부족한 경우                                                                   |345       |      |                |
|700   |Authorization through tx.origin                        |tx.origin을 이용한 인증                                                               |477       |      |                |
|701   |Weak Sources of Randomness from Chain Attributes       |난수의 무작위성이 약한 경우                                                                 |330       |      |                |
|702   |Hash Collisions With Multiple Variable Length Arguments|가변 길이의 인자를 hash에 사용하여 특정한 상황에서 충돌 발생 하는 경우                                    |294       |      |                |
|703   |Untrusted Source                                       |신뢰할 수 없는 source로부터 값을 받아온 경우                                                   |          |      |                |
|800   |Integer Overflow and Underflow                         |Integer의 범위를 넘어 연산하는 경우 발생하는 보안약점                                               |682       |      |< 0.8.0         |
|801   |Floating Points and Precision                          |실수 연산의 정밀도 문제가 발생하는 경우                                                          |1339      |      |                |
|802   |Incorrect Calculation                                  |잘못된 수식을 사용한 경우                                                                  |682       |      |                |
|803   |Incompatibility with Deflationary Tokens               |Deflatinoary Token을 고려하지 않은 경우                                                  |841       |      |                |
|804   |Incorrect exchange of value                            |잘못된 가치 교환(withdraw <-> burn)                                                    |682       |      |                |
|900   |Typographical Error                                    |오타로 인한 보안 약점이 발생하는 경우                                                           |480       |      |                |
|901   |price manipulation                                     |자산의 가격이 조작 가능한 경우                                                               |          |      |                |
|902   |honeypot by scanner                                    |scanner의 특징을 이용한 허니팟                                                            |207       |      |                |
|903   |Disclosure of information                              |공개되면 안되는 정보의 유출                                                                 |          |      |                |
|904   |Incorrect calculation of value                         |잘못된 asset value 계산                                                              |682       |      |                |
|905   |Governance design flaw                                 |거버넌스 설계 결함                                                                      |          |      |                |
|906   |Frontend vulnerability                                 |프론트 취약점                                                                         |          |      |                |
|907   |Logic bug                                              |위 분류에 포함 되지 않으면서 취약점으로 작용할 수 있는는 것들                                                  |          |      |                |

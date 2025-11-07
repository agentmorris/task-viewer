# Issues

## Task A - P0 E1 S0

Default sort weight for P0 E1

P0
E1
S0
!test

## Task B - P0 E1 S10

Higher sort weight, should appear first among P0 E1 tasks

P0
E1
S10
!test

## Task C - P0 E1 S-5

Lower sort weight, should appear last among P0 E1 tasks

P0
E1
S-5
!test

## Task D - P0 E2

No sort weight specified, default to 0

P0
E2
!test

## Task E - P1 E1 S100

High sort weight but P1, should appear after all P0 tasks

P1
E1
S100
!test

## Task F - P0 E1 S5

Mid-range sort weight

P0
E1
S5
!test

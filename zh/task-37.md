银行业务为我们提供了许多有趣的编程问题，与你之前学习的[储蓄计算器](https://www.codeabbey.com/index/task_view/savings-calculator)相比，下面这一个更为复杂。

After Joel bought a boat he has got the new idea - to buy a house. Since he did not want to wait until necessary sum is collected, he considers a mortgage, which is to get a loan from bank and buy a house immediately, while loan is secured by this house (i.e., in case of borrower's default bank gets the house in compensation).

Joel 在购买了一艘船后又有了一个新的想法 - 再买个房子。由于他不想等到凑够全款的时候再购买，
Mathematically, mortgage works by the following algorithm:

Joel borrows big money sum P from bank (and performs purchase);
bank tells him its interest rate R in percents - the speed of growth of the debt;
at the end of each month the debt is increased by R / 12 percents;
immediately after it Joel gives to bank some predefined small sum M to decrease the debt;
debt is considered settled when its value is reduced to zero (this could take several years).
For example, Joel takes P = $800,000 from bank with interest rate of R = 6%. He is willing to pay M = $10000 at the end of each month.

Month     P        P * (R/12)%      -M       new P
  1    $800000       $4000       -$10000    $794000
  2    $794000       $3970       -$10000    $787970
  3    $787970       $3940       -$10000    $781910
 ...
 12    $732325       $3662       -$10000    $725987
 ...
 24    $654138       $3271       -$10000    $647408
 ...
 103     $4188         $21        -$4209         $0
So after 103 months (which is about 8.5 years) the debt could be payed out. The last payment of course could be less than M (since P need not to become negative). Note that he will pay out about:

102 * $10000 + $4209 = 1024209
which is 25% more than the cost of the house.

Joel asks you (the mighty programmer) to help him with the calculation of necessary monthly payment M.

Input data contains values for loan size P, interest rate R and length of time to pay out L in months.
Answer should contain the required monthly payment M rounded up to whole dollars (i.e. if you get non-integer result, increase it to nearest integer which is greater).

Example:

input data:
800000 6 103

answer:
9957
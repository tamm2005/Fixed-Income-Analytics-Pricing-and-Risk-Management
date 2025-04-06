# Fixed Income Analytics: Pricing and Risk Management

- This course is a study of fixed income securities from an anlytical perspective.
 - We are concered with rigorous quantitative methods for the valuation and risk management of these assets
Fixed income securities are debt instruments
- Our main focus will be bonds and money market instruments. Chirfly we will be concerned with government debt.
- More than any other asset, class, interes rates are a prime concern in the study of fixed income securities
- Thus the study of interesrt rates will be another core component of this course
- The main assets whose study will drive the material in this course are treasury bonds, treasury bills, strips, and repurchase agressments
- Note that treasury here refers to the debt of any government- but US government securities will be our main source of examples
- To market for US Treasury securities is the largest and most liquid bond market in the world, so one has to make it a chief focus
- However, the analytic principles and techniques we study in this course are applicable to all bond markets, and we will consider examples from other markets as well
- The valuation of bond, both coupon bonds and zero coupon bonds like tyrasuery bills and strips, will be a primary focus of the course
- Bond pricing goes hand in glovewith interest rates, so a deep study of the term structure of interest rates will be another central concern
- We will study the linkage between bond prices and interest rates
- In the process, we will also review the main theories of the term structure, the pure expectations hypothesis and the liquidity (risk) premium hypothesis
- Risk is one of the central concepts of finance, and some of the deepest material in this course will involve the study of the risk of fixed income securities
- We will study the classic bond risk meaures, dollar duration, DV01, duration, and convexity
- This course is intended for practitioners, whether budding or already in the business, and applications are the main driver of everything we do in this course
- We will treat applications to bond trading, covering topics like riding the yield curve, and rate level trading, and risk management applications like immunization and applications in asset/liability management
- In addition to the main financial material, Python codes are included as part of the course, implementing all the techniques treated
- The Python codes are released under a permissive MIT license and yare yours to take and use in your own work
- They provide a powerful compl;ement to the core course material, based on hand calculations whihc students can get extensive practice with the included problem sets and detailed solutions

# Interest Rates
- Interest ratyes are measures of the price charged in the economy to borrow money
- **Terminology**: The charge levied to borrow money is called interest
- **Principal** is the amount of money borrorwed in a loan. 
- The **interest rate** is the fraction of the principal of a loan that will be charged as interest per unit time
- The time unit implicit in an interest rate is called the **time basis** of the interest rate
- An **annual** or **annualized interest rate** is an interest rate for which the time basis is 1 year
- Quoted interest rates are usually annual interest rates. In this course interest rates are always annualized

Suppose we take olut a loan for $X$ (ie Principal = $X$) at an annual interest rate of r
If we hold the load for 1 year how much interest will we be charged?
We have $r=$ fraction of $X$ charged per year $=$ percentage of $X$ charged per year.
Express $r$ as decimal, then

**<p align="center">**
Total 1 Year Interest $=rX$
</p>
and if we make no payments, then our total debt after 1 year is

**<p align="center">**
Outstanding Debt = Principal + Interest= $X+ rX$ = $(1+r)X$
</p>

**Example**: Suppose we borrow $5000 at an annual interest rate of 7\%. How much interest will we be charged in the first year? How much will our debt have accumulated to after 1 year if we make no payments?
The interest rate is $r$=$7\%$=$0.07$ <p>
1 year of interrest on $5000 is

**<p align="center">**
1 Year Interest $=$ $(0.07)(5000)$ $=$ ${\$350}$
</p>

After 1 Year, our total debt is
**<p align="center">**
1 Year Total Debt $= (1+0.07)(5000) = {\$5350}$
</p>

The previous calculation embeds a few assumptions. One assumption is that the interest is calulated exactly once, one the original principal, and is charged to the borrower exactly once during the year This is an example of annual compounding conventions such as semiannual, monthly, or continuous compounding. The previous example was cast from the perspective of a borrower. One may also look at interest rates from the point of view of a saver or investor

# Simple Interest
- The interest rates we have considered so far were, in effect, examples of simple interest rates
- Simple interest is interest that is levied only on thje original principal
- In particular, no interest is ever charged on the accumulated interesrt at any time. That is, there is no compounding

**Example**: Suppose a bank loans $10,000 out at a simple interest rate of 7% for 10 years. What total interest will the bank be paid?

The interest charged is 7% of $10,000 oer year for 10 years:

**<p align="center">**
Total Interest $=$ $(10)(0.07)(10,000)$ $=$ ${\$7,000}$
</p>

In general, if will load or invest a principal $F$ at the simply compounded interest rate $r$ for a duration of $T$ years, the total interest paid will be

**<p align="center">**
Total Interest $=rTF$
</p>

and the total value of the investment at the end of the period is

**<p align="center">**
Total Investment Value = initial principal + interest
$=F+rTF
=(1+rT)F$
</p>

Note that there is nothing in this argument that requires $T$ to be an integer number of years, and simple interest is most commonly used for loan or investment terms less than 1 year

In the case of an investment term equal to a fraction of a year, the convention is to write the term as

**<p align="center">**
$T=\frac{days}{365}$
</p>

where days are the number of days of the investment term, so that the total interest is

**<p align="center">**
$T=\frac{days}{365} \times rF$
</p>

and the total investment value at the end of the term is

**<p align="center">**
$\text{Total Investment Value}
=(1+r\times \frac{days}{365}) \times F$
</p>

**Remark**: This varies, depending on the daya count convention

**Example**: If you invest $50,000 at a simple interest rate of 4% on July 15, how much is your investment worth on September 30 of the same year?

To use the previous formula we must compute the number of days in the investment peruiod, from July 15 to September 30.

From July 15 there are 31-15=16 days left to the end of July, +31 days in August, +30 days to Sept 30. :

**<p align="center">**
$\text{days}=16+31+30=77$
</p>

With a principal of $F=\$50,000$ and interest rate of $r=4\%$:

**<p align="center">**
$\text{Final Investment Value}=(1+0.04 \times \frac{77}{365}) \times \$50,000=\$50,423$
</p>

# Compound Interest
- With simple interest, the interest rate is only ever applied to the original principal, interest is never paid on accumulated interest
- This limits the growth potential under simple interest
- Compounding interest is the act of adding interest to the principal so that interest is now charged on interest previously paid
- The most basic case of compounding is annual compounding
- **Annually compounded interest** is interest that is added to the principal once per year so that interest in the next year is levied on the interest charged so far as well as the principal

Suppose $r$ is an annually compounded interest rate.

Suppose the principal $F$ is invested at this rate.

The interest accrued after 1 year is

**<p align="center">**
$\text{fisrt year's interest}=rF$
</p>

At the end of the first year, we add this interest to the original principal, so that the updated principal after 1 year is

**<p align="center">**
$\text{1 year interest}= \text{original principal}+\text{interest}=F+rF=(1+r)F$
</p>

This is now treated as the principal for the purposes of the next interest rate calculation. This is the event of compounding.

The interest for the second year is calculated by applying the interest rate $r$ to the updated principal:

**<p align="center">**
$\text{second year's interest}= r(1+r)F$
</p>

If we now add this to the 1 year principal, the new principal after 2 years:

**<p align="center">**
$\text{2 year principal}= \text{1 year principal} +\text{2nd year interest} = (1+r)F+(1+r)F= (1+r)^2F$
</p>

ONe may continue this process year by year, and it is not hard to see (eg. by induction) that after K years, the total principal is 

**<p align="center">**
$V(K) = (1+r)^KF$
</p>

**Example**: The most familiar circumstance involving compound interest is a deposit in a savings account. Suppose you decide to deposit your life savings of $100,000 in a savings account that pays 6% interest compounded annually. What is the balance in your account in 20 years if no withdrawals are made? How much of this balance is interest? How much is interest on interest?

With an annually compounded interest rate of 6%=0.06, the value of the investment in 20 years is

**<p align="center">**
$\text{Value in 20 year}=(1+0.006)^{20}\times \$100,000=\$320,714$
</p>

The total interest is this final value minus the initial principal invested:

**<p align="center">**
$\text{interest}=\text{final value}-\text{original principal}=\$320,714-\$100,000=\$220,714$
</p>

The interest earned only on the principal is 20% per year for 20 years

**<p align="center">**
$\text{interest on principal}=20 \times 0.06 \times \$100,000=\$120,000$
</p>

 The interest on interest is then

**<p align="center">**
$\text{interest on interest}=\text{interest}-\text{interest on principal}=\$220,714-\$120,000=\$100,714$
</p>

- **Semiannual Compounding**: The process of semiannual compounding is identical to annual compounding, except that the compounding event occurs twice per year
Fro a semiannualy compounded rate $r$, the interet accrued after 6 months is added to th principal at that time:

**<p align="center">**
$\text{updated 6 month principal}=\text{principal}+\text{6 month interest}=F+\frac{rF}{2}=(1+\frac{r}{2})F$
</p>

(Note that while r is semiannually compounded, it is an annualized rate, so the intereszt for 1 year is $rF$ and for 6 months is $rF/2$)

After this the process is the same as for annual compounding, resulting in a total investment value after $t$ years as

**<p align="center">**
$V(T)=(1+\frac{r}{2})^{2T}F$
</p>

**Example**: Suppose the semiannually compounded interest rate is 4%. Compute the value of a $50,000 investment invested at this rate in 1 year, and in 30 months. What interest rate would result in an investment worth $58.000 in 18 months, and in 3 years?

In 1 year:

**<p align="center">**
$\text{Investment Value}=(1+\frac{0.04}{2})^{(2)(1)} \times \$50,000=\$52,020$
</p>

In 30 months:

**<p align="center">**
$V(5/2)=(1+\frac{0.04}{2})^{(2)(5/2)} \times \$50,000=\$55,204$
</p>

To grow the investment in 18 months:

**<p align="center">**
$(1+\frac{r}{2})^{(2)(5/2)} \times \$50,000=\$58,000$  
$r=0.1014345=10.14\%$
</p>

In 3 years:
**<p align="center">**
$V(3)=(1+\frac{r}{2})^{(2)(3)} \times \$50,000=\$58,000$  
$r=0.0501=5.01\%$
</p>

- **Periodically Compounded Interest**: Using argumenets similar to the semiannually compounded case (Left to exercises), we may derive the future valuer for rates coumpounded $k$ times per year

In the case that $r$ is an interest rate compounded $k$ times per year, the future value of an initial investment $X$ is

**<p align="center">**
$V(T)=(1+\frac{r}{k})^{kT}X$  
</p>

Special cases of note are:

**<p align="center">**
$\text{Quarterly Compounding}: V(T)=(1+\frac{r}{4}^{4T})X$  
$\text{Monthly Compounding}: V(T)=(1+\frac{r}{12}^{12T})X$    
</p>

# Continuous Compounding
- Continuous compounding corresponds to instantaneous compounding of all interest is paid on it
- Mathematically it is the limit of periodic compounding as the compounding frequency goes to infinity
- There are significant mathematical advantages to working with continuously compound rates, and it is often preferred representation of interest rates

From the last lectute, we have the formula for the $T$ year investment value under a $k$ times per year compounded rate $r$:

**<p align="center">**
$V(T)=(1+\frac{r}{k})^{kT}X$  
</p>

Recall the limit from calculus:
**<p align="center">**
$\lim_{k \to \infty}(1+\frac{x}{k})^k=e^x$  
</p>

Using this formula, take the limit as $k$ goes to $\infty$ in the expression for $V(T)$:
**<p align="center">**
$\lim_{k \to \infty}(1+\frac{r}{k})^{kT}=e^{rT}$  
</p>

Thus with continuous compounding, the future value of an investment of $X$ in $T$ years is
**<p align="center">**
$V(T)=e^{rT}X$  
</p>

**Example**: Suppose the contnuously compounded interest rate is $r=5\%$. Calculate the value of a $20,000 investment at this rate in 6 years. What continuously compounded rate would result in an investment worth $30,000 in 10 years

The future value of the investment is
**<p align="center">**
$V=e^{(0.05)(6)}(20,000)=\$26,997$  
</p>

To grow the investment to $30,000 in 10 years requires
**<p align="center">**
$e^{r \times 10} \times \$20,000=\$30,000$  
$r=0.04054=4.05\%$
</p>

**Rate Conversions**: As fro periodic compounding, conversions are possible between continuously compounded rates and periodically compounded rates

If $r$ is a continuously compounded rate and $r_k$ is the equuvalent periodically compounded rate with compounding frequency $k$, then

**<p align="center">**
$r=klog(1+\frac{r_k}{k})$  
</p>

gives the continuously compounded rate and 

**<p align="center">**
$r_k=k(e^{r/k}-1)$  
</p>

Gives the periodic rate
Proofs and applications are in the problems

# Investment Return Measures
 - The notion of investment return or return on investment (ROI) refers to some measure of the profit or loss realized on  an investment
 - Let $V(t)$ be the value of some investment at time $t$. In particular, $V(0)$ is then the initial investment commited by an investor
 - In this lecture, we will assume that investments do not pay any income or dividends, and be concerned solely by capital gains or losses
 - We will consider returs over a given investmetn horizon, denoted by $T$
- We can consider **absolute** and **relative** measures of return on investments
- An absoulte measure of return would usually be expressed as a dollar value, sometimes going by the name dollar return
- The most baic example of an absolute return measure is the profit and loss **(P & L)**:

**<p align="center">**
$\text{P\&L}=V(T)-V(0)$  
</p>

- Most of the most useful return measures are relative return measures
- On simple relative return measure is the **gross return**:

**<p align="center">**
$\text{gross return}=\frac{V(T)}{V(0)}$  
</p>

- Perhaps the most basic return measure is the quantity $R$ defined by the equation

**<p align="center">**
$1+R=\frac{V(T)}{V(0)}$  
</p>

- This return measure can be called a relative return, a percentage return, or a rate of return
- In the course $R$ will be called the **return**, or the **cumulative return**
- **Remark**: We will sometimes use the terminology rate of return, but it will mean something somewhat different

With return so defined,

**<p align="center">**
$1+\text{return}=\frac{V(T)}{V(0)}$  
</p>

We get an explicit expression by solving the equation:

**<p align="center">**
$\text{return}=\frac{V(T)}{V(0)}-1=\frac{V(T)-V(0)}{V(0)}=\frac{\text{P\&L}}{V(0)}$  
</p>

Thus the return is the profit or loss of the investment expressed as a fraction or percentage (if we multiply by 100) of the original investment

As the name suggests, this quantity is the most basic of all return measures
**Remark**: Note that return and gross return are rekated hrough the identity:

**<p align="center">**
$\text{return}=\text{gross return} - 1$  
</p>

THus the gross return conatins exactly the same information as the return

**Example**: Suppose you invest $12,000 at an annually compounded interest rate of 9%. Using an investment horizon of 3 years, calculate your R&L, gross return, and return


We have $V(0)=$12,000$ and:

**<p align="center">**
$V(3)=\$12,000(1+0.09^3)=\$15,540$  
</p>

Thus:

**<p align="center">**
$\text{P\&L}=\$15,540-\$12,000=\$3540$  
$\text{gross return}=\frac{\$15,540}{\$12,000}=1.295$  
$\text{return}=\frac{\text{P\&L}}{12,000}=0.295=29.5\%$
</p>

- **Annualized Returns**: Annualized returns are meaures of return per unit time

Mathematically, they are averages of the returns realized over successive intervals of time over the duration of the investment

We continue to denote our investment horizon by $T$. We define the **annualized return** by $\rho$ such that

**<p align="center">**
$(1+\rho)^T=\frac{V(T)}{V(0)}$
</p>

which we may solve for $\rho$:

**<p align="center">**
$\rho=[\frac{V(T)}{V(0)}]^{\frac{1}{T}}-1$
</p>

We will sometimes refer to $\rho$ ad the rate of return

**Exmaple**: Calculate the annualized return in the previous example.

The annualized return is

**<p align="center">**
$\rho=(\frac{15,540}{12,000})^{\frac{1}{3}}-1=0.09=9\%$
</p>

Is this a coincidence?

**Interest Rates and Returns**: Of course, the answer to that question is no

Suppose we invest an amount of money $X$ at an annually compounded interest rate $r$ for $K$ years

Tha value of the investment at the end of the investment period is

**<p align="center">**
$V(K)=(1+r)^KX$
</p>

and the annualized return is 


**<p align="center">**
$\text{annualized return}=[\frac{(1+r)^KX}{X}]^{\frac{1}{K}}-1=1+r-1=r$
</p>

The relationship between interest rates, compounding conventions, and returns is explored further in problems

# Coupon Bonds
- This course is concerned primarily with debt securities, and the dominant  form of debt security traded on markets today is the bond
- A bond or debt security is a contract that a borrowing entity offers to enter into with potential bond buyers
- The borrower is said to *issue* the bond and is thus referred to as the **bond issuer**. The counterparty is called the **bond holder**
- The bond holder pays the bond issuer to enter into the contract, and in return the bond issuer is obligated to make preschduled payments to the bond holder
- What distinguishes this form  a mere loan is that bonds are tradeable instruments: The bond holder can sell the right to receive the payments to someone else  

As a financial instrument he most general form of a bond can be described and modelled in the following way

There are preset times
**<p align="center">**
$t_1,t_2,...,t_N$
</p>

and corresponding to these times preset cash flows
**<p align="center">**
$c_1,c_2,...,c_N$
</p>

which are paid by the bond issuer to the bond holder

From the bond holder's (bond investor's) point of view, a bond is the right to receive this stream of cash flows

The payments of a bond with cash flows $c_1=c_2=\$10$, $c_3=c_4=\$10$ and $c_5=\$100$, paid at dates $t_1=i$ years for $i=1...5$

- Most issued bonds fall into the category of **coupon bonds**, which are specified by a set of key parameters
- The **face value** which can also be called the **par value** or**principal** or the **nominal value** of the bond and plays the role of the principal of the loan
- The **maturity** of the bond is the date the contace terminates. At or about the maturity date, the face value is paid to the bond holder
- Prior to maturity, the bond issuer makes interest payments to the bond holder
- The **coupon rate** is the interest rate of the bond and is paid to the bond holder annually, with the coupon payments sometimes split into multiple payments over the course of a year
- Of tcoupone bonds, one particular structure is by far the most prevalent, known as **vanilla bonds**, or **bullet bonds**
- As this is the bond structure we will mostly be concerned with, we will establish the notation we will generally use for these bonds

The face value of the bond will be denoted $F$. The annual coupon will be denoted $c$. The coupon rate is thus $c/F$

If the payment frequency is $k$ then the cash flows are $c/k$ paid at reguarly spaced intervals $k$ times per year

By far the most common payment frequencies are $k=1$ (annual) and $k=2$ (semiannual)

**Example**: Suppose it is June 20, 2019. What are the payments and payment dates of a 7% coupon bond, making semiannual payments , with a face value of $100,000, and maturing in 5 years?

The annual payments total
**<p align="center">**
$\text{annual coupon}=7\% \times \$100,000 = \$7000$
</p>

This payment is split into 2 semiannual coupon payments of 
**<p align="center">**
$\frac{7000}{2}=\$3500$
</p>

Assuming the bond matures on June 20, 2024, the following is the schedule of payments:
| Date      | Payment |
| :---        |    :----:   |
| 12/20/2019      | $3500       |
| 6/20/2020   | $3500       |
| 12/20/2020   | $3500        |
| 6/20/2021   | $3500        |
| 12/20/2021   | $3500        |
| 6/20/2022   | $3500        |
| 12/20/2022   | $3500        |
| 6/20/2023   | $3500        |
| 12/20/20203   | $3500        |
| 6/20/2024   | $3500+$100,000=$103,500        |

- **Zero Coupon Bonds**: Technically, a zero, coupon bond can be considered a special case of a coupon bond: it is simply a coupon bond whih makes exactly one payment, on the maturity date
- While this is mathematically correct, it violates the spirit of what we mean by a "coupon bond" so we consider it a distinct class of securities
- Nevertheless zero coupon bonds are of fundamental importance in fixed income analysis, and are a building block for the entire subject
- In fact, coupon bonds are, technically, portfolios of zero coupon bonds

**Example**: Plot the payments of a zero coupon bond with a $10,000 face value and a maturity of 5 years

The bond simply makes one payment of $10,000 in the 5th year after origination of the bond

# Bond Pricing
- Bonds's have other defining features besides the contactual deatils (maturity, face value, coupon) we have condifered so far
- ONe of these is the bond's price. The price of a bond is the outcome of marktet activity, rather than being an intrinsic or contractual feature of the bond
- But how does the marktet price a bond? What factors influence a market's assessment of the value of a bond?
- As an asset, a bond is the right to receive a certain stream of payments at certain times over the life of the bond
- So the market price of a bond is the market's assessment of the economic value of that stream of cash flows
- Relating a stream of future payments to value right now is a fundamental concept in finance, the *time value of money*
- This is the topic of the nextion session
- We may still use the idea of bond price in a comparative way

We note that the nominal value of a bod can be regrarded as the "quantity" of a particular bond
For instance, a $20,000 nominal value of a bond entitles the bond holder to exactly 2 times the cash flos of $10,000 nominal value of a bond with the same characteristics (coupon rate and maturity)

This suggests that the $20,000 bond's price should be exactly 2 times the $10,000 bond's price

**Example**: Suppose a US treasury bond maturing in 2 years paying 8% coupons (semiannually) and with a face value of $30,000 is currently trading for $25,000. Comapre the payments of this bond with those of another 2 year treasury with 8% coupons and a $120,000 nominal value. What is the market value of the $120,000 treasury? What about for a $10,000 treasury?

The $20,000 treasury pays an annual coupon of

**<p align="center">**
$\text{annual coupon}=0.08 \times \$30,000=\$2400$
</p>

which is split into 2 semiannual payments of $1200 each paid every 6 months

The final payment at maturity adds the last coupon payment to the $30,000 face value

Thus the payments are:
 Date      | Payment |
| :---        |    :----:   |
| 6 months      | $1200       |
| 1 year   | $1200       |
| 18 months   | $1200        |
| 2 years  | $31200        |

The $120,000 treasury has a nominal value exactly 4 times that of the $30,000 treasury

And since it also pays 8% coupons, its interest payments will also be 4 times those of the $30,000 treasury, as we may verify:

**<p align="center">**
$\text{payments}=\frac{0.08 \times \$120,000}{2}=\$4800$
</p>
which is 4 times the $1200 payments of the first bond
It s payments are thus:

 Date      | Payment |
| :---        |    :----:   |
| 6 months      | $4800       |
| 1 year   | $4800       |
| 18 months   | $4800        |
| 2 years  | $124,800        |

The above plot shows that all the payments for the $120,000 bond are in proportion (by a factor of 4) to those of the $30,000 bond

Holding this bond is equivalent to holding a portfolio consisting of 4 units of the first bond

Thus it is not surprising that the correct price of this bond is exactly 4 times the price of the Z$30,000 bond:

**<p align="center">**
$\text{price of \$120,000 bond}=4 \times \$25,000=\$100,000$
</p>

We note that, while this would be the correct answer according to financial principles, in practice, it might not be so simple

There are, for instance, liquidity issues for the larger position which may make it difficult to sell the 4 times larger position for exactly 4 times the smaller one

The $10,000 bond has exactly $1/3$ the nominal value of the original bond, so by similar reasoning, its payments will be $1/3$ those of that bond:

 Date      | Payment |
| :---        |    :----:   |
| 6 months      | $400       |
| 1 year   | $400       |
| 18 months   | $400        |
| 2 years  | $10,400        |

And by similar reasoning its price will be $1/3$ that of the $30,000 bond:

**<p align="center">**
$\text{price of \$10,000 bond}=\frac{\$25,000}{3}=\$8333$
</p>

It is convention in many markets to quote bond prices per $100 nominal value
That is, the price is quoted for a $100 nominal value on the given bond, and then it is scaled up for the bond with a different face value

This effectively means that the bond's price is reported as a percentage of the nominal value

When this convention is followed, the bond price is expressed as plain number with no dollar ($) sign

**Example**: Suppose a bond's price (per $100 notional) is 83. What is the price of $15,000 nominal of this bond? What is the nominal value of this issue an investor owns if she invests $1,000,000

Since a price of 83 is quoted for this issue, the price of eht given position will be

**<p align="center">**
$P=\frac{83}{100}\times \$15,000=\$12,450$
</p>

The price of a $100 nominal of this bond is $83, so if an invesor spends $1,000,000 worth of the bond, she buys

**<p align="center">**
$\frac{1,000,000}{83} \times \$100 = \$1,204,819$
</p>

**Remark**: In this course we eill not, by default, follow this convention. When we have a bond asset with a particular face value we will report (and calulcate) the price for the given nominal value, without normalizing it to $100. In those cases where we do chooose to follow this pricing convention, it will be made clear by quoting a price as a raw number rather than as a dollar value-in particular, there will be no dollar(\$) sign.

For instance, if a bond price is reported as 95 (rather than 95), this implies that it is the price per $100 nominal value

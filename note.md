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
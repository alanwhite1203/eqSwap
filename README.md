# Equity Swap Product and Valuation

An equity swap is an OTC contract between two parties to exchange a set of cash flows in the future. Normally one party pays the return based on capital gains and dividends realized on an equity security and the other party pays the return based on a floating interest rate plus a spread. 
An equity swap can be used to transfer both the credit risk and the market risk of an underlying asset. Equity swaps can be also used to avoid transaction costs (including Tax), to avoid locally based dividend taxes, limitations on leverage (notably the US margin regime) or to get around rules governing the particular type of investment that an institution can hold. Equity swaps can make investment barriers vanish and help an investor create leverage. 
Equity swaps allow parties to potentially benefit from returns of an equity security without the need to own its shares. In general, a party enters an equity swap with the objective of either obtaining return exposure or hedge existing equity risk for a period of time. 
The two cash flows are usually referred to as "legs" of the swap. The leg referred to as the floating leg is pegged to a floating rate such as LIBOR. The other leg of the swap referred to as the equity leg is based on the performance of either a share of individual stock or stock index. 
The party receiving the total returns gains exposure to the performance of the reference asset without actually owning the asset; hence this instrument can be used to obtain a leveraged exposure. On the other hand, the party receiving payments based on the reference rate receives protection against a loss in the value of the underlying equity. Unlike other swap types, the equity swap notional resets on each cash flow reset date, depending on the performance of the underlying asset.
Equity swaps allow parties to potentially benefit from returns of an equity security without the need to own its shares. In general, a party enters an equity swap with the objective of either obtaining return exposure or hedge existing equity risk for a period of time. This presentation gives an introduction to equity swap product and valuation. 

	Equity Swap Introduction
	An equity swap is an OTC contract between two parties to exchange a set of cash flows in the future. Normally one party pays the return based on capital gains and dividends realized on an equity security and the other party pays the return based on a floating interest rate plus a spread. 
	The party receiving the total returns gains exposure to the performance of the reference asset without actually owning the asset; hence this instrument can be used to obtain a leveraged exposure.
	On the other hand, the party receiving payments based on the reference rate receives protection against a loss in the value of the underlying equity. 
	Unlike other swap types, the equity swap notional resets on each cash flow reset date, depending on the performance of the underlying asset.

	The Use of Equity Swap
	Equity swaps allow parties to potentially benefit from returns of an equity security without the need to own its shares.
	In general, a party enters an equity swap with the objective of either obtaining return exposure or hedge existing equity risk for a period of time. 
	An equity swap can be used to transfer both the credit risk and the market risk of an underlying asset. 
	Equity swaps can be also used to avoid transaction costs (including Tax), to avoid locally based dividend taxes, limitations on leverage (notably the US margin regime) or to get around rules governing the particular type of investment that an institution can hold.  
	Equity swaps can make investment barriers vanish and help an investor create leverage.

	Valuation
	There are two legs in an equity swap: an equity leg and a floating interest leg. 
	The payoff for both legs could be set at every reset date or at maturity; or could be one side at maturity and the other at every reset date. 
	The price of the swap is the difference between the present values of both legs' cash flows. In other words, the present value of swap is net of present value of "equity leg" and "money market leg".

The present value of an equity leg is given by
〖PV〗_equity (t)=N∑_(i=1)^n▒〖[(S_i-S_(i-1))/S_(i-1) ] D_i 〗
where
	t   –  the valuation date
	N  – the notational principal amount
	i  –  the ith cash flow from 1 to n
	D_i=D(t,T_i)  –  the discount factor
S_i=[S-〖PV〗_i (D)] e^(r_i (T_i-t) )   - the equity forward price
	S – the equity spot price at valuation date
	〖PV〗_i (D)=∑_(t<τ<T_i)▒〖d_τ e^(-r_τ (τ-t) ) 〗   - the present value of all dividends between t and T_i
	d_τ – the discrete dividend paid at τ where t ≤ τ ≤ T
	r_i – the continuously compounded interest rate from t to T_i

The present value of a floating interest rate leg can expressed as
〖PV〗_floating (t)=N∑_(i=1)^m▒〖(F_i+s)τ_i D_i 〗
where
	t   –  the valuation date
	N  – the notational principal amount
	i  –  the ith cash flow (swaplet) from 1 to n
	τ_i=τ(T_(i-1),T_i) – the accrual period (T_(i-1),T_i) of the ith cash flow.
	D_i=D(t,T_i)    –  the discount factor
	   F_i=1/τ_i  (□(D_(i-1)/D_i -1))- the simply compounded forward rate
	s  - the floating spread

The present value of the equity swap from the equity receiver perspective is given by

	PV(t)=〖PV〗_equity (t)-〖PV〗_floating

	Practical Note:
	We consider discrete dividends only as described in <equity future>. 
	To value an equity swap, you need to generate cash flows first, based on the start time, end time and payment frequency of the leg, plus calendar (holidays), business convention (e.g., modified following, following, etc.) and whether sticky month end.
	Second, an interest rate curve needs to be constructed via the most liquid interest rate instruments. <> provides useful tools to construct various curves and volatility surfaces.
	Then, you need to compute equity forward prices correctly by accounting for all discrete dividends. This is a key factor for all equity related valuation.
	Accrual period is calculated according to the start date and end date of a cash flow plus day count convention 
	Forward rate is continuously compounded rather than other compounding types

	A Real World Example
Equity Leg	Interest Rate Leg
Currency	USD	Currency	USD
Initial Price	164.38	Leg Type	Float
Start Date	2/15/2017	Day Count	dcAct360
Maturity Date	8/15/2017	Notional	4931400
Shares	30000	PayReceive	Receive
Notional	4931400	Start Date	2/15/2017
PayReceive	Pay	Maturity Date	8/15/2017
Payment Frequency	1M	Payment Frequency	1M
Underlying	737446807=	Spread	0.0075
		Index Definition
		Index Day Count	dcAct360
		Index Tenor	1M
		Index Type	LIBOR


You can find more details at
https://finpricing.com/lib/FxVolIntroduction.html

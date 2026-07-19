
Generally speaking, my philosophy here was to account for and separate revenue by type -- both for our internal understanding and to then accurately model each revenue type going forward based on available information.

Lines 19 through 27 are derived from our contracts and Stripe.

19 - All plans - realized revenue coming from tiered pricing plans (starter, professional, business)
22 - Overages - realized revenue coming from minutes above the number of allotted minutes in a contract
25 - Net New ARR - newly contracted annual contracts by month
26 - Sum of line 25
27 - Existing annual contracts before October 2024

Lines 11-15 normalize this data into an annualized contracted revenue.

Lines 3-8 model future revenue. Contract revenue is modeled from pipeline, then from planned account executive hires and existing and new partnerships. Expansions are modeled off of 24% NRR, which may be low given current overages ($X). Plans are modeled on a simple growth rate.
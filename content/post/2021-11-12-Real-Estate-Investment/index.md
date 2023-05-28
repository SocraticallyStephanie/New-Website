---
title: 'Finding the Best Real Estate Investments in the Current Market'
date: "2021-06-05T00:00:00Z"
authors:
- admin

categories:
- Finance
- Programming

tags:
- Investing

featured: true
reading_time: true
draft: true

markup: mmark

image:
  placement: 2
  preview_only: false
---

In the real estate market, among so many opportunities, it takes work to identify which ones are the best from a financial point of view. Investors often rely on their intuition and knowledge of the market to determine the best deals based on the listed real estate prices. In this context, a good deal would be a property bought for a reasonable price, below the market price.

However, knowing the exact market price of a flat requires good modeling of market transactions based on the intrinsic characteristics of the flat. Moreover, the price of an apartment is only one component of the whole financial equation. We can use a comprehensive approach to buying, renovating, and selling real estate leveraged by data science. We show our rationale to identify which properties are good opportunities (best risk-return ratio).

## Internal Rate of Return

The **Internal Rate of Return (IRR)** is defined as the compounded rate of return on an investment. It is implied interest rate as which the initial capital investment must have grown to reach a desired result. The IRR is calculated as follows:

$$IRR = \frac{FV}{PV}^{\frac{1}{n}}-1$$

where $FV$ is the future value (the expected nominal amount), $PV$ is the present value (the initial investment), and $n$ is the investment's duration. 

There are more methodical and mathematical ways to calculate the IRR, but it is very tedious, so I won't go over them here. Instead, you can think about the IRR as a representation of the Net Present Value (NPV) in the form of a percentage. The NPV is the present value of all future cash flow earned from an investment, which is discounted to the present at a rate that reflects the risk of the investment.

The formula is shown below:

$$NPV=\sum_{t=0}^{n}\frac{CF_{t}}{(1+r)^{t}} = \frac{CF_{1}}{(1+r)^{1}}+\frac{CF_{2}}{(1+r)^{2}}+\ldots+\frac{CF_{n}}{(1+r)^{n}}-IV$$

where $CF$ are the cash flows earned from the investment at time $t$, $r$ represents the discount rate (and for our purposes $r=IRR$) and the $IV$ is the initial investment. The NPV is a prevalent metric used in capital budgeting and real estate to determine which investments to take. Typically, if the NPV of a project is positive (a number greater than zero), it is worth pursuing, and vice versa for a negative NPV.

The IRR is the interest rate that would make the NPV equal to zero.

$$0=NPV=\sum_{t=0}^{n}\frac{CF_{t}}{(1+r)^{t}} $$

To calculate the IRR of an apartment that will go through the process of purchase, renovation, and sale, in New York, investors should pay attention to the following events:
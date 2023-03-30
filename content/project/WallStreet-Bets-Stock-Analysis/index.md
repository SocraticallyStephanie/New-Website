---
title: Does a r/WallStreetBets Portfolio Significantly Outperform?

authors:
- admin

summary: No, but we can watch some interesting stock pitches and learn some valuable lessons
tags:
- Finance
- Statistics
- Data Science
date: "2022-10-05T00:00:00Z"
markup: mmark

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.


draft: false
reading_time: true
---

Thanks to the prevalence of COVID-19 in our everyday lives, it's getting increasingly difficult to return to normal for most people. While I've used this additional flexibility to pick up on old hobbies (gaming, music, etc.), others have used theirs to learn about financial markets. Knowing that I work in finance, some of my friends have reached out to me for financial pointers, while others have opted for the convenience of reading r/WallStreetBets.

You may be asking, why am I -- someone who would be considered a "sophiscated investor" -- would even be interested in a platform such as r/WallStreetBets? For those of you who don't know, I've written a piece about the subreddit last year. However, it was never clearly explained the buzz around r/WallStreetBets.

Due to the pandemic (the financial insecurity and flexibility it brought to millions of people), as well as the stimulus checks provided by the government and the rise of free trading platforms such as Robinhood, a lot of people who would typically not dabble with stocks are having fun with the stock market. They're also investing in all sorts of zany things like Dogecoin and GameStop. Institutional Investors (the "smart money") and the veterans in the financial media fail to understand this, and they're generally condescending and negative towards these new brand of retail investors.

They call them idiots for taking risks in cryptocurrencies; they call them fools for believing companies in dying industries with falling revenues are great investments [[2](#2)]. From this, the term "Dumb Money" was used to describe this new breed of investors; "DOGE/GME to the moon," they frequently chant, much to the disdain and confusion of legacy investors and their friends in the legacy media [[3](#3)].

Recognizing the condescension, these retail investors decide to take their agency back using the self-described label known as **Retards**. **Retards**, if you don't know, is a rearrangement of the word **tradeRS**. Since they're not considered legitimate **tradeRS** in the eyes of the investment community, they'll just call themselves **Retards**, which is an anagram designed to reclaim the agency taken from retail investments. Sure, they may be considered "Dumb Money," but they're going to make the investment decisions they want to without the influence and manipulation of institutional investors and their friends in the financial media.

This is largely the energy behind drama involving r/WallStreetBets and the rest of the investment community.

## Are r/WallStreetBets Stock Picks Even Any Good?

It is generally assumed -- rightly or wrongly -- that if you have a background in finance, you know what you're talking about. The barriers required to work within the industry seem to justify the claim. The most well-known front-end finance jobs require a bachelor's degree at an accredited four-year university, along with passing, at minimum, the Securities Industry Essentials Exam (or SIE) and either a FINRA Series 3 or 7 Exam. 

Jobs that are more analytically driven, such as Actuaries, may require candidates to have a statistical or mathematical background and pass several SOA (Society of Actuaries) Exams. While Quants (which is my domain) typically don't require examinations; however, some positions do encourage and require candidates to have at minimum a Masters of Science in a STEM field.

So yes, it may be easy to see why people on Wall Street are considered "Smart Money."

However, this doesn't mean you need education and fancy certificates to make good investments.  Warren Buffett, one of the greatest investors alive, began to invest on his own when he was only 11-years-old. While the man would never even look at any of the companies r/WallStreetBets are investing in, he established a system that allowed him to make sound investments using the resources available at the time; namely, a book published by Benjamin Graham called The Intelligent Investor. Speaking from personal experience, I started learning about finance and economics on my own time before I enrolled in university to pursue it as a career.

Today, the resources available to help retail investors are potentially endless. Most of what you'll find on the internet is bunk; however, you can find invaluable information if you know where to look.

This project aims to see if the **TradeRS** at r/WallStreetBets know where to look. Are they seeing things we aren't seeing or just larping as wall street speculators?

## What Are "Meme Stocks"?

A meme stock is a stock that has seen an increase in volume not because of how well the company performs, but rather because of hype on social media and online forums. For this reason, these stocks often become overvalued, seeing drastic price increases in just a short amount of time.

Many of these stocks have not performed well in recent years. Some of these stocks may exist in struggling retail or brick-&-mortor (GME) industries. Other stocks may have once been considered leaders in their respective industries but have rebranded and shifted their focus to maintain viability (BBY). However, one common thing among these meme stocks is that they all follow the same life cycle.

![image](meme-stock-life-cycle.jpg)

"To the moon" was a popular rallying cry for many holders of these stocks. It was used as a reminding, regardless of how much the price may drop, buy and never sell, because we (retail investors) control the value of the stock, and not institutional investors. There is no doube that it can be exciting to make money day trading and to be part of something bigger than yourself. 

Unfortunately, there is still a large body of research that suggest that even the most experienced of day traders lose money [[4](#4)].

## Building a "Meme Stock" Portfolio

![Result](02.PNG)

We will construct a portfolio using popular stocks from the WallStreetBets community. In July 2021, I decided to find the most talk-about stocks in the r/WallStreetBets subreddit and narrowed the list down to 20 of the most popular equities on the platform. Six of these assets have recently gone public, and they will be excluded from the experiment.

We're also going to include popular cryptocurrencies, such as Bitcoin and Dogecoin.


### Seeking Alpha

Alpha, or Jensen's Alpha, quantifies the excess returns obtained by a portfolio of investments above the returns implied by the Capital Asset Pricing Model (CAPM).

The formula is denoted as follows:

$$r_{\alpha} = r_{f} + \beta_{\alpha} * (r_{m}-r_{f})+\epsilon$$

where:

* $r_{f}$ = Risk Free Rate
* $\beta$ = Beta of a security
* $r_{m}$ = Expected market return
* $\epsilon$ = Tracking error

This formula can be better understood if we refactor the formula as seen below:

$$(r_{\alpha}-r_{f})=\beta_{\alpha}*(r_{m}-r_{f})+\epsilon$$

The left side of the equation gives us the difference between the asset return and risk-free rate, the "excess return." If we regress the market excess return against the asset excess return, the slope represents the asset's beta. Therefore, beta can also be calculated by the equation:

$$\beta=\frac{Cov(r_{a},r_{b})}{var(r_{b})}$$

So beta can be described as:

$$\beta=\rho_{a,b}*\frac{\sigma_{a}}{\sigma_{b}}$$

The formula above shows that beta can be explained by the correlated relative volatility. To make this simplier, beta can be calculated by doing a simple linear regression which can be viewed as a factor to explain the return, and the tracking error can represent alpha.

The value of alpha -- the excess returns -- can vary. A positive number signal's overperformance relative to the benchmark, while a negative number signals underperformance. Zero (or a number close to zero) shows a neutral performance; the fund tracks the benchmark.

The CAPM formula utilizes the risk-free rate to account for risk. Therefore, if a given security is fairly priced, the expected returns should be the same as the returns estimated by CAPM. However, if the security were to earn morethan the risk-adjusted returns, the alpha should be positive.

## Descriptive Statistics (Risk & Return)

So how does our meme stock portfolio perform?

![alpha](alpha.png)

As we can see, most of the stocks in our portfolio outperform the S&P 500 by a modest margin. Out of the 20 assets, 8 of them outperform our benchmark at least 1%, and 3 have underperformed our benchmark. If we average the , it comes out to 0.9386, which means that our meme stock portfolio only outperforms the S&P by 0.93% (I got this figure by simply averaging the  for each asset). So, should you invest in a portfolio like this? I suppose it "depends" on your income goals and overall suitability (after all, this isn't investment advice).

If I'm a college student, probably majoring in economics/finance with an interest in quant finance, and I'm just experimenting with investment strategies, I might be grateful that my strategy is at least slightly better than the S&P. However, if I'm a grown adult looking generate wealth, I don't think I would be satisfied with 0.93%, which barely accounts for management fees.

Granted, those who consider meme stocks a sound investment are usually self-taught and were first introduced to investing during the AMC/GME/DOGE craze. Needless to say, they are probably managing their own portfolios (no management fees for them). It may be difficult to quantitatively comprehend the idea of an  0.93, especially when so many assets can perform much better.

![beta](beta.png)

As mentioned before, most assets (especially stocks) are positively correlated with the broader market. Most of the assets in our portfolio have $\beta$ greater than 1, which means they are more volatile than the overall market. As we see, CLF has a $\beta$ of 1.7, which means we can expect this stock to increase by 1.7% for every 1% increase in the broader market.

## Portfolio Optimization

We have shown that our meme stock portfolio outperforms the S&P 500 by 0.93%, but that doesn't mean it will typically outperform our benchmark by this amount. This amount can change, based on the size of our portfolio, as well as how we weigh each asset. We can figure out how to best do this, by utilizing the Modern Portfolio Theory (MPT). The MPT is a method for selecting investments in order to maximize their overall returns within an acceptable level of risk.

Essentially, we are trying to find the most efficient portfolio possible.

How do we measure the efficiency? We measure it with another formula known as the Sharp Ratio. The Sharpe ratio measures the performance of an investment compared to a risk-free asset, after adjusting for its risk. The sharpe ratio can be calculated by the following:

$$Sharpe Ratio = \frac{R_{p}-R_{f}}{\sigma_{p}} $$

The greater the Sharpe ratio, the better, as it indicates that an instrument's returns are large relative to its risk. Also, the greater the Sharpe ratio, the higher the earnings on average than the risk-free rate.

![beta](portfolio.png)

Now we've allocated all 20 of our assets based on our risk tolerance. As you can see, our program has plotted 100,000 unique portfolios, with annualized returns ($\alpha$) on our y-axis and annualized volatility ($\beta$) on our x-axis. It's possible to select a random portfolio inside the curve, but there will always be some portfolio out there, with the same number of assets, that will outperform in terms of returns and risk. The optimal or efficient portfolio will always exist somewhere on the edge of the curve, hence, the efficient frontier.

If we want the least about of risk possible, using our selected 20 instruments, we should allocate most of our funds towards BBBY, RNG, TWNK, TX, USA, X, HCA, VRTX, and BTC. These 9 instruments will comprise 77.4% of the portfolio. By allocating the portfolio in this way and prioritizing risk, we will achieve an excess annualized return (our $\alpha$) and volatility of 0.3.

What if we only care about maximizing return? If we want the greatest return possible, using the same 20 instruments, we should allocate most of our funds towards AMC, CLF, GME, BB, TWNK, SAVA, HCA, BTC, and DOGE. These assets will comprise ~75% of our portfolio. Using this optimal portfolio allocation which prioritizes returns, our portfolio achieves an annualized return of 0.84, with a volatility of 0.51.

So compared to the descriptive statistical analysis we've used earlier, we've actually **OVERSTATED** our return for this portfolio. Using the most optimal allocation method possible, with thousands of different possibilities, we find that our meme stock portfolio still barely *outperformes* our benchmark.

In practical terms, it would be difficult for a serious investor to justify building a portfolio with these 20 assets when there are so many different investments out there that could do significantly better for the least amount of risk. This is especially true if you're trying to avoid investing in assets that appear to be overvalued, such as Bitcoin and GameStop.

## Lessons From The Meme-Stock Craze

I doubt this analysis will convince anyone apart of r/WallStreetBets, TradeRS, or anyone sympathetic to the meme-stock trading "revolution." Much has been written about the heroic campaign by individual investors to slay giant institutional investors. It's easy to understand why this narrative is compelling, so I doubt anyone would want to listen to someone with institutional experiences, such as myself. Regardless, there are still valuable lessons that can be learned from the meme-stock craze, and the effort to democratize financial markets misses the market on many of these lessons.

First, it's dangerous for investors to follow crowds in stock markets or any need. r/WallStreetBets initiated campaigns to inflate asset prices past their intrinsic value or their long-term fundaments, making opportunities such as GameStop, AMC, and Bed, Bath & Beyond appear to be attractive investment opportunities. But those who bought these stocks close to their peaks are already nursing losses as the shares have come down. Overpaying for stock prices that don't reflect business fundamentals isn't courageous. Many who bought into the hype are already learning this painful lesson on the risk of market fads.

Second, the Federal Reserve has played an unwitting role creating an enviroment where the meme-stock challenge can happen. In the Fed's efforts to stabilize the economy, money has become virtually free. Ultralow interest rates encourages people to borrow and to take bigger risk to seek better returns. As a result, we've seen record sums of money being pumped into SPACS (special purpose  acquisition corporations) and private equity funds. As more money chases more opportunity, there are more instances of companies coming to market without being fully-vetted.

Third, the cheap money also fuels record retail trading activity. We've seen this movie before, and it rarely ends well; for those of us who remember the dot-com frenzy in the late 1990s and the mortgage bubble that led to the 2008 financial crisis. With the Fed increasing interest rates to combat persistently high inflation, they will have to reluctantly deflate any bubbles that have emerged. We're venturing onto uncharted territory, where our rookie investors now have to learn to generate alpha in an environment without cheap money and a zero-lower bound.

As such, quality is the best recipe for returns. Focusing on high-quality companies is a good defence against irrational market moves. And companies that enjoy strong organic growth drivers aren't beholden to the hypercompetitive M&A market for growth. Building an equity portfolio based on businesses with sustainable earnings growth is a recipe for consistent outperformance and reduced volatility, even in a world where smaller investors can mount powerful campaigns to shock market leaders.

[<a name="2">2</a>] [The New York Times | 'Dumb Money' is on GameStop, and It's Beating Wall Street at Its Own Game ](https://www.nytimes.com/2021/01/27/business/gamestop-wall-street-bets.html)

[<a name="3">3</a>] [Quartz | Reddit and Robinhood gamified the stock market, and it’s going to end badly](https://qz.com/1966818/with-gamestop-reddit-and-robinhood-gamified-the-stock-market/)

[<a name="4">4</a>] [Hass School of Business, University of California Berkley | Do Day Traders Rationally Learn About Their Ability?](https://faculty.haas.berkeley.edu/odean/papers/Day%20Traders/Day%20Trading%20and%20Learning%20110217.pdf)
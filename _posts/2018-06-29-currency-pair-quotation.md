---
title: Currency Pair Quotation
use-site-title: true
mathjax: true
---

直接标价法，间接标价法，基础货币/报价货币，报价货币/基础货币 ……  我知道，无非一个是另一个的倒数，但是谁是谁呢？

*Direct quote, indirect quote, base currency, indirect currency, B/P, P/B, ... I know, ultimately, one is another's reciprocal. But, who is who?*

## Always Step 1: Figure out the Base Currency

The first step is figure out which currency is the *base currency*, or the currency that stays as one unit in the quote.

###### Example 1.1

rate $\approx$100, between USD and JPY $\implies$ base currency = USD

###### Example 1.2

rate $>$ 1.0, between USD and GBP $\implies$ base currency = GBP

**The base currency is always the one that serves as one unit.**

**Once the base currency is set, there should be no controversy about the figure in the quote, no matter it is a direct or indirect quote, written in the B/P or P/B manner.**

###### Example 1.3

base currency = USD, between USD and JPY $\implies$ rate $\approx$ 100

确定基础货币永远是弄清汇率报价的第一步，一旦确定了哪个货币是基础货币，对于报价的数字将不会有任何争议。

无论是直接标价法、间接标价法，还是写成$\dfrac{\text{基础货币}}{\text{报价货币}}$或是$\dfrac{\text{报价货币}}{\text{基础货币}}$，基础货币一确定，报价的数字就确定了。

#### Q1: What is the other currency called, besides the base currency?

Either *price currency*, or *quote currency*, or, simply, *counter currency*.

与基础货币相对应的是报价货币。

## Step 2: Direct Quote or Indirect Quote

**Whether it is direct quote or indirect quote largely depends on where you are.**

| Direct Quote                           | Indirect Quote                          |
| -------------------------------------- | --------------------------------------- |
| uses foreign currency as base currency | uses domestic currency as base currency |

###### Example 2.1

rate $\approx$ 100, between USD and JPY

in New York $\implies$ indirect quote

in Tokyo $\implies$ direct quote

直接标价法还是间接标价法，取决于报价者的角度。

#### Q2: Why it is called direct / indirect quote, not the other way round?

Focus on foreign currency.

|                                  | direct quote               | indirect quote               |
| -------------------------------- | -------------------------- | ---------------------------- |
| **shows**                        | price of foreign currency  | quantity of foreign currency |
| **larger quote means**           | expensive foreign currency | cheap foreign currency       |
| **tells foreign currency value** | directly                   | indirectly                   |

- Direct quote is a *price* quote, which tells the value of a foreign currency *directly*. 

- Indirect quote is a *quantity* quote, which tells the value of a foreign currency *indirectly*. 

- 直接标价法直接标出了外币的（本币）价格。

- 间接标价法标示的是等值（单位本币的）外币的数量，间接反映了外币的价值。

## Step 3: Ways to Express a Currency Pair

You may have noticed that up to this point I haven't written anything like USD/JPY. There could have been no confusion at all, were it not for the fact that people in the academia and people in the markets stick to two opposite expressing manners.

你可能注意到了，到目前为止，我还没有写任何像是$\dfrac{USD}{JPY}$ 这样的内容。事实上，如果不是学界和业界坚持要用两套不同的写法，这本来不会引起任何混淆。

The first thing to make clear is that whether to put base currency in the numerator or denominator has nothing to do with direct/indirect quote. Honestly, to me this is the chief culprit for most of the confusion. 

首先要弄明白，把基础货币放在分子还是分母的位置，和直接或是间接标价法无关。实话说，我认为这是引起误解和混淆的最大来源。

| Market Convention<br />市场习惯                              | (Certain) Academic Convention (like in CFA textbooks) <br />（某些）学术习惯（例如CFA教材） |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| $\dfrac{B}{P}$ or $\dfrac{\text{Base Currency}}{\text{Price Currency}}$ | $\dfrac{P}{B}$ or $\dfrac{\text{Price Currency}}{\text{Base Currency}}$ |

That is, for a quote that's around 100 between USD and JPY, which is an indirect quote in New York, the market convention is to express it as USD/JPY, while in certain textbooks it may be JPY/USD.

Luckily, the convention is consistent across the market. In fact, the market is so sure about this that they define base currency as the first currency that appears in the currency pair.

也就是说，同样是报价数字为100左右的美元、日元汇率，同样（在纽约）为间接标价法，市场的写法是$\dfrac{USD}{JPY}$，而某些教材的写法却可能是$\dfrac{JPY}{USD}$。

好在外汇市场本身对于报价的写法是统一的。事实上，外汇市场对于基础货币的定义就是：出现在外汇报价对中的第一种货币。

#### Q3: How to interpret the expression?

For market convention (B/P), it is a ratio of value:

业界的写法（即$\dfrac{\text{基础货币}}{\text{报价货币}}$）是价值的比值：

$$
\Big[ \dfrac{\text{USD}}{\text{JPY}} \Big]_{\tfrac{B}{P}} = \dfrac{\text{Value of 1 USD}}{\text{Value of 1 JPY}} \approx 100
$$

For certain academic convention in the opposite manner, it has merit, too -- it resembles the way in physics, like $m/s$, so that it may mingle with standalone currency units. Say you exchange US$ 2.5 to Japanese Yen:

学界某些相反的写法（即$\dfrac{\text{报价货币}}{\text{基础货币}}$）也自有它们的道理。

这种写法很像是物理上面的单位，像米/秒，这样它们就能与货币单位混合使用。例如你将2.5美元换成日元：

$$
2.5 \ \text{USD} \times \ \Big[ \dfrac{\text{JPY}}{\text{USD}} \Big]_{\tfrac{P}{B}} \approx 2.5 \ \text{USD} \times  100 \ \dfrac{\text{JPY}}{\text{USD}} = 250 \ \text{JPY}
$$



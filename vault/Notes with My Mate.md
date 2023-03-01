---
id: c77uo335fzt81rmc69hw9x0
title: Notes with My Mate
desc: ''
updated: 1675108488394
created: 1675107737971
---

Our recent topic: textual analysis on Finance and the McDonald word list and NLP.

I am surpised at how finance people are doing their textual analysis. Of course, all the filings are extremely useful albeit the outdated methods. 

[This AWS paper is pretty nice.](https://www.sciencedirect.com/science/article/pii/S2405918821000131) Yet,
my mate said it failed to provide insights on how this would help finding returns. Apparently, the returns are more important than methods to come up with better word lists.

Here are more to read for me to understand how textual analysis works in finance:

[Some lit review on advanced textual analysis](https://www.sciencedirect.com/science/article/pii/S2405918822000046)

[Another important work from McDonald](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2504147)

I also have to start working on gathering datasets and data cleaning.

[[Notes with My Mate.todolist]]

2023.03.01 Update

Researched on [FinBert](https://arxiv.org/pdf/1908.10063.pdf) and [FinBert from HKUST](https://github.com/yya518/FinBERT). Processed some basic disclosure texts with FinBert. 

Our findings: 
1. FinBert does not actually perform better than Vanilla Bert. 
2. When the text is long, we split texts use paragraph breaks and calculate weights from the paragraph lenghts. This metric works better than average. It makes much more sense as well.

Next step:
Extract texts from 10-K and use BERT to extract features from them. To solve our previous issue with data, we found EDGAR which supplies API and online host for all the SEC filings we need and this open-source tool [SEC-EDGAR-text extraction](https://github.com/alions7000/SEC-EDGAR-text) for text extraction for the filings. 

Some other useful links:
[sec-edgar python library](https://github.com/sec-edgar/sec-edgar)

[python-edgar: master index for edgar](https://github.com/edgarminers/python-edgar)



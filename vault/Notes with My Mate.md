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

-----------------
2023.03.01 Update

Researched on [FinBert](https://arxiv.org/pdf/1908.10063.pdf) and [FinBert from HKUST](https://github.com/yya518/FinBERT). We've also processed some basic disclosure texts with FinBert. This paper [What are You Saying? Using topic to Detect Financial Misreporting](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2803733) can guide us on retrieving misreport judgements from SEC. The author Richard Crowley has done a symposium sharing on using BERT to predict return, which is exactly what we are looking for.

Our findings: 
1. FinBert does not actually perform better than Vanilla Bert. 
2. When the text is long, we split texts use paragraph breaks and calculate weights from the paragraph lenghts. This metric works better than average. It makes much more sense as well.

Next step:
Extract texts from 10-K and use BERT to extract features from them. To solve our previous issue with data, we found EDGAR which supplies API and online host for all the SEC filings we need and this open-source tool [SEC-EDGAR-text extraction](https://github.com/alions7000/SEC-EDGAR-text) for text extraction for the filings. 

Some other useful links:
[sec-edgar python library](https://github.com/sec-edgar/sec-edgar)

[python-edgar: master index for edgar](https://github.com/edgarminers/python-edgar)

-----------------
2023.03.05 Update

SEC filings make sense because of the tables and numbers, not particularly the texts. So we have to use number-aware BERT, such as [SEC-BERT](https://huggingface.co/nlpaueb/sec-bert-base). Some other people fine-tuned it on [classification task](https://huggingface.co/nickmuchi/sec-bert-finetuned-finance-classification).

Crowley used [OpenIE](https://nlp.stanford.edu/software/openie.html) to extract information and ontology from the texts. But probably going on step further, making it a knowledge graph and add weights on the edges would be more helpful.

So with this inspiration, we are looking at some new directions today:

[heatmap generation](https://github.com/jiesutd/Text-Attention-Heatmap-Visualization)

[knowledge graph skg](https://github.com/danilo-dessi/skg)

[knowledge graph kgen](https://github.com/rossanez/KGen)

[Bert + Knowledge Graph on legal data](https://github.com/AnjaneyaTripathi/knowledge_graph)

[Text to KG](https://github.com/d1egoprog/Text2KG)

[From unstructured text to knowledge graph](https://github.com/rutvik5/knowledge-graph)

[graphGPT](https://github.com/varunshenoy/GraphGPT)

[Standford CoreNLP](https://stanfordnlp.github.io/CoreNLP/demo.html)
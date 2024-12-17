
# ISPRAS News Datasets Collection

- [Dataset For Information Extraction From News Web Pages](#Dataset-For-Information-Extraction-From-News-Web-Pages)
  - [Dataset Description](#dataset-description-1)
  - [Data Collection](#data-collection-1)
  - [Dataset Format](#dataset-format-1)
  - [Download](#download-1)
  - [Citation](#citation-1)
- [NewsListDataset](#NewsListDataset)
  - [Dataset Description](#dataset-description-2)
  - [Dataset Format](#dataset-format-2)
  - [Download](#download-2)


## Dataset For Information Extraction From News Web Pages

Multilingual dataset of labeled news web pages for information extraction task.

<h3 id="dataset-description-1">Dataset Description</h3> 

Dataset contains websites in 44 languages. We labeled such attributes on news web pages: *title*, *publication date*, *text*, *authors*, *tags*. Some sites may also have *subtitle*, *sources* and *categories* annotations.

We presented the statistics for the number of sites, pages and labeled nodes in the [AE_DATASET_STATS.md](./AE_DATASET_STATS.md) file.

We also have a separate dataset for Russian news sites. We labeled there *title*, *subtitle*, *publication date*, *modification date*, *text*, *authors*, *sources*, *categories* and *tags*.

<h3 id="data-collection-1">Data Collection</h3> 

For multilingual dataset, we marked up nodes on pages using sitemaps created with the [Web Scraper](https://github.com/ispras/web-scraper-chrome-extension).

Creating the Russian dataset is described in our [paper](https://ieeexplore.ieee.org/document/10076872). The annotators marked up web pages using Label Studio according to the [guideline](./MANIFEST.md).

<h3 id="dataset-format-1">Dataset Format</h3> 

For the multilingual dataset we have JSON for each language with the following structure:
```
{'site': [
  {
    'uuid':
    'url':
    'html':
    'annotations': [
      {
        'xpath':
        'text':
        'label':
      },
      ...]
  },
  ...],
...}
```

JSON structure for the Russian dataset is the Label Studio JSON MIN format:
```
[
  {
    'id':
    'url':
    'html':
    'html_en':
    'agency':
    'site':
    'title':
    'annotator':
    'annotation_id':
    'created_at':
    'updated_at':
    'lead_time':
    'labels': [
      {
        'text':
        'hypertextlabels':
        'start':
        'end':
        'endOffset':
        'startOffset':
        'globalOffsets':
      },
      ...]
  },
...]
```
We additionally added `html_en` with translated HTML into English.

<h3 id="download-1">Download</h3> 

* Multilingual dataset (8.4 GB): [`multilingual-ae/`](https://nextcloud.ispras.ru/index.php/s/gkttoE637s9kxfJ)
* Multilingual web pages in MHTML (zipped 43.9 GB): [`multilingual-ae-mhtml.zip`](https://nextcloud.ispras.ru/index.php/s/RbxBaq3P7MD9DCC)
* Multilingual web pages in HTML (zipped 1.5 GB): [`multilingual-ae-html.zip`](https://nextcloud.ispras.ru/index.php/s/L2DTDdkRfwmy4PS)
* Russian dataset (178 MB): [`russian.json`](https://nextcloud.ispras.ru/index.php/s/fHgbox8mZYkQkew)
* Russian web pages in MHTML (zipped 1 GB): [`russian-ae-mhtml.zip`](https://nextcloud.ispras.ru/index.php/s/xm7NGX7bya7W8eo)

<h3 id="citation-1">Citation</h3> 

More details about the Russian-language dataset are available in our [paper](https://ieeexplore.ieee.org/document/10076872). Please cite us if you use or discuss this dataset in your work:
```
@INPROCEEDINGS{10076872,
  author={Varlamov, Maksim and Galanin, Denis and Bedrin, Pavel and Duda, Sergey and Lazarev, Vladimir and Yatskov, Alexander},
  booktitle={2022 Ivannikov Ispras Open Conference (ISPRAS)}, 
  title={A Dataset for Information Extraction from News Web Pages}, 
  year={2022},
  volume={},
  number={},
  pages={100-106},
  keywords={Annotations;Neural networks;Web pages;Data aggregation;Information retrieval;Data mining;Electronic commerce;web data extraction;information extraction;news;webpage dataset;neural networks},
  doi={10.1109/ISPRAS57371.2022.10076872}}
```

## NewsListDataset
Dataset for extracting news records with their attributes from html pages. 

<h3 id="dataset-description-2">Dataset Description</h3> 

This dataset contains pages with lists of news in Russian.
The following attributes were marked: *title*, *date*, *tag*, *short_text*, *time*, *short_title*, *author*.

Their distribution:

|             | Pages | Records | Domains |
|-------------|-------|---------|---------|
| title       | 12679 | 247262  | 275     |
| date        | 12296 | 241634  | 251     |
| tag         | 6165  | 108400  | 140     |
| short_text  | 6855  | 115983  | 138     |
| time        | 1938  | 41892   | 8       |
| short_title | 105   | 1289    | 4       |
| author      | 87    | 957     | 1       |

Totally dataset contains 13099 pages.

<h3 id="dataset-format-2">Dataset Format</h3> 

Each file from data folder is instance of json dictionary with fields:
* **html**: formatted html code of page
* **exist_labels**: labels which are located at html
* **domain**: domain of page
* **labeled_xpaths**: dictionary of xpaths and its labels
* **timestamp**: timestamp of date, when page was loaded
* **url**: url of page
* **record_xpaths**: xpaths of block-nodes (first text node of each record)

<h3 id="download-2">Download</h3> 

* NewsListDataset (915 MB): [`russian.json`](https://nextcloud.ispras.ru/index.php/s/ZP4D8cjAs4FcAjx)

This file is dump of python-like list object, each item of it is instance of dictionary with fields described at [Dataset Format](#dataset-format-2). So the size of list is 13099 items.
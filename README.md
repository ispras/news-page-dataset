
# ISPRAS News Datasets Collection

<summary>Datasets:</summary>

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

Multilingual dataset of labeled news web pages for information extraction task

<h3 id="dataset-description-1">Dataset Description</h3> 

Dataset contains websites in 6 languages: Russian, English, German, Chinese, Korean, Arabic. We labeled news pages with attributes from these sets:
* For Russian: title, subtitle, publication date, modification date, text, authors, sources, categories, tags
* For other languages: title, publication date, text, authors, tags

<table>
  <thead>
    <tr>
      <th></th>
      <th></th>
      <th>Title</th>
      <th>Text</th>
      <th>Date</th>
      <th>Author</th>
      <th>Tag</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">ru</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">112 / 722</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>110<br>712<br>714</td>
      <td>112<br>716<br>5918</td>
      <td>110<br>708<br>724</td>
      <td>54<br>262<br>272</td>
      <td>49<br>332<br>1190</td>
    </tr>
    <tr>
      <td rowspan="2">en</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">10 / 500</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>10<br>500<br>500</td>
      <td>10<br>499<br>22200</td>
      <td>10<br>499<br>499</td>
      <td>4<br>147<br>147</td>
      <td>2<br>98<br>258</td>
    </tr>
    <tr>
      <td rowspan="2">de</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">9 / 450</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>9<br>450<br>454</td>
      <td>9<br>449<br>6847</td>
      <td>9<br>450<br>600</td>
      <td>9<br>270<br>308</td>
      <td>2<br>100<br>336</td>
    </tr>
    <tr>
      <td rowspan="2">zh</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">10 / 500</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>10<br>500<br>501</td>
      <td>10<br>500<br>5872</td>
      <td>10<br>500<br>500</td>
      <td>6<br>227<br>277</td>
      <td>0<br>0<br>0</td>
    </tr>
    <tr>
      <td rowspan="2">ko</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">10 / 500</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>10<br>500<br>500</td>
      <td>10<br>500<br>6898</td>
      <td>10<br>500<br>550</td>
      <td>8<br>358<br>409</td>
      <td>1<br>41<br>155</td>
    </tr>
    <tr>
      <td rowspan="2">ar</td>
      <td style="text-align: center">Sites / Pages</td>
      <td colspan="5" style="text-align: center">10 / 500</td>
    </tr>
    <tr>
      <td>Sites with attribute<br>Pages with attribute<br>Nodes with attribute</td>
      <td>10<br>500<br>500</td>
      <td>10<br>500<br>5752</td>
      <td>10<br>500<br>550</td>
      <td>10<br>180<br>274</td>
      <td>4<br>184<br>648</td>
    </tr>
  </tbody>
</table>


<h3 id="data-collection-1">Data Collection</h3> 

Creating the Russian-language part of the dataset is described in our [paper](https://ieeexplore.ieee.org/document/10076872). The annotators marked up web pages using Label Studio according to the [guideline](./MANIFEST.md).

For other languages, we marked up nodes on pages using sitemaps created in the [Web Scraper](https://github.com/ispras/web-scraper-chrome-extension).

### Dataset Format {#dataset-format-1}

For Russian-language part we have JSON file with the following structure (Label Studio JSON MIN format):
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

JSONs structure for other languages:

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

<h3 id="download-1">Download</h3> 

* Multilingual dataset (1.1 GB): [`annotations/`](https://nextcloud.ispras.ru/index.php/s/zbaDqkxmQPmaEkT)
* Russian-language web pages in MHTML format (zipped 1 GB): [`news-page-dataset-mhtmls.zip`](https://nextcloud.ispras.ru/index.php/s/YDwme8jSByQY2xC)


<h3 id="citation-1">Citation</h3> 

More details about the Russian-language part of the dataset are available in our [paper](https://ieeexplore.ieee.org/document/10076872). Please cite us if you use or discuss this dataset in your work:
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
The following attributes were marked: title, date, tag, short_text, time, short_title, author.

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
* **record_xpaths**: xpaths of block-nodes(first text node of each record)

<h3 id="download-2">Dataset Format</h3> 

Dataset available at: 
* NewsListDataset (915 MB): [`russian.json`](https://nextcloud.ispras.ru/index.php/s/ZP4D8cjAs4FcAjx)

This file is dump of python-like list object, each item of it is instance of dictionary with fields described at [Dataset Format](#dataset-format-2) . So the size of list is 13099 items.
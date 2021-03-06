# Knolml-Analysis-Package
The aim of this project is to do various types of analysis on knolml which can be used by a reseracher who is working on wikipedia data.

## Analysis1: Controversy Analysis using wiki-links
To measure the relative controversy level of various wiki-links present in a wikipedia article.

Module: from kml_analysis_pkg import controversy

Input Format: controversy.run(input_file_name)

Example: controversy.run("sample.knolml")

## Analysis2: Contributions of an author over a given period of time in a wikipedia article
To find contributions of an author in terms of words, sentences, bytes etc over a given period of time (given starting and ending dates)

Module: from kml_analysis_pkg import author_contribution

Input Format: author_contribution.run("sample.knolml", start_date, end_date, measure_option)

Date Format: YYYY-MM-DD

Measure Options: sentences/bytes/wikilinks/words

Example: author_contribution.run("sample.knolml", "2000-01-01", "2010-01-01", "words")

## Analysis3: Ranking all the authors based on their contribution to a given paragraph
To rank all the authors of a wikipedia article based on their contribution to a particular paragraph present in the article. The paragraph will be given as input to the program.

Module: from kml_analysis_pkg import author_para_contribution

Input Format: author_para_contribution.run(input_file_name)

Example: author_para_contribution.run("sample.knolml")

## Analysis4: Finding external knowledge gaps in a wikipedia article
A wikipedia article represents knowledge about some related topics, like a wikipedia article on IIT Ropar may be talking about placements of IIT Ropar in a particular section. But, in this section there was no information regarding a new branch say Biotechnology which was newly introduced. So, can we write a Python program that can tell that the information regarding placements of Biotechnology is missing from the IIT Ropar wikipedia page? Or in general can we tell that there is a knowledge gap in a wikipedia article?

Module: from kml_analysis_pkg import external_gaps

Input Format: external_gaps.run(input_file_name, word_vector_model)

Word Vector Model: Pretrained model avaiable at https://github.com/parasKumarSahu/Knolml-Analysis/blob/master/Text-Segmentation/wrdvecs-text8.bin

Example: external_gaps.run("GeneralScience.txt", "wrdvecs-text8.bin")

## Analysis5: Finding internal knowledge gap in a wikipedia article
Internal Knowledge Gap arise due to difficulty in understanding of an article. We define various readability prameter and compute them for thousands of articles to study how these parameters affect the overall readability of a wikipedia article.

### To download featured articles(sorted by page views):-

Module: from kml_analysis_pkg import downloader_featured

Input Format: downloader_featured.run(path_of_html_file)

html_file avaiable at https://github.com/parasKumarSahu/Knolml-Analysis/tree/master/Wiki%20Featured%20Articles%20Downloader

Example: downloader_featured.run("Wikipedia Featured articles - Wikipedia.htm")

### To download B, C, GA, Start and Stub articles:-

Module: from kml_analysis_pkg import downloader_from_titles

Input Format: downloader_from_titles.run(path_of_file_containing_list_of_articles)

Example: downloader_from_titles.run("B")

### To calaculate readability parameters:-

Module: kml_analysis_pkg import internal_gaps

Input Format: internal_gaps.run(path_of_folder_containing_articles, word_vector_model)

Word Vector Model: Pretrained model avaiable at https://github.com/parasKumarSahu/Knolml-Analysis/blob/master/Text-Segmentation/wrdvecs-text8.bin

Example: internal_gaps.run("test", "wrdvecs-text8.bin")

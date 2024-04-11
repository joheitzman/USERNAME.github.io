---
layout: post
title: First Post and Instructions for Posting
date: '2024-04-10'
categories: Update, Misc.
tags: 
---

First, double-click the file named "post_template.sh".

You will be prompted to write down:

1. A title (this will be the title of your post)
2. Your categories (this can be anything from 'methods' to 'new findings')
3. Your tags (e.g. PROT, ROS, DNA, etc.)

Your page will then look like this:

---  
layout: post  
title: 'your title here'  
date: '2024-04-10'  
categories: 'your categories here'  
tags: 'your tags here'  
---  

*note: you can use "---" to make a line break*  

Your notebook entry will come after this section.  
To add spacing between lines, you can either have an empty line on both sides of the sentence, or just add a double-space at the end/beginning  
There are several different ways to add flair to your entry:  
* = bulletpoint  
1. 1.(with a space), 2., 3., = numbered list/bulletpoint
2. just some text
3. and some more text

```placing text between three apostrophes changes its appearance```


# = Big Title using "#"
## = Subtitle using "##"
**bolded text within double asterisks**  
*italicized text within single asterisks*

Below is if you want to link something from the internet

[tag/website name](link)
e.g. [marine biochem](https://www.marinebiochemresearch.com/)

*note: when linking to a file, you need to upload it to the folder labelled '_data' first.*
*another note: in the code, keep the download text & link lines separated by at least one empty line*  

If you want to post a picture, first, upload the photo to the folder labelled 'images'   
Then it can be accessed by using the following code with your filename at the end:  

<img src="{{ https://github.com/LizaRoger/LizaRoger.github.io }}/images/stock_chemist.jpg">



# Converting CSV files to tables
1. first, input your csv file into the folder labelled _data
2. then, format the first line of the code below with your filename in the place of 'example_data'

 {% assign table_rows = site.data.example_data %}

  <table>
      {% for row in table_rows %}
          {% if forloop.first %}
              <tr>
                  {% for pair in row %}
                      <th>
                          {{ pair[0] }}
                      </th>
                  {% endfor %}
              </tr>
          {% endif %}

          {% tablerow pair in row %}
              {{ pair[1] }}
          {% endtablerow %}
      {% endfor %}
  </table>

For file accession and downloads, first, upload your file to the folder labelled 'files'  
Then, adjust the code below to include your filename and it should now be a download link

some text and [here is possible to download the file][1]

[1]:{{ https://github.com/LizaRoger/LizaRoger.github.io }}/files/GitHub_ELN_paper.pdf

Or, maybe you want an embed PDF within your post
Then, just adjust the path in the code below to contain your file within the folder 'files'

<embed src="{{ https://github.com/LizaRoger/LizaRoger.github.io }}/files/GitHub_ELN_paper.pdf" width = 1000 height = 500>

## You can view the code used for this post in either Github (Preview/Code), or through a third-party app. I use notepad++, but choose whatever you're familiar with.
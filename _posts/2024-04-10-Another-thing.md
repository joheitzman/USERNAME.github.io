---
layout: post
title: Another thing
date: '2024-04-10'
categories: Data
tags: RNA
---

These should be bullet points
	1. The first thing
		a. The other thing
			1a. The last thing
	2. Another thing
	And these are bullet points without numbers
		Likewise
			and another

## This is a big title
# This is another title
This is normal text
1. These are steps
2. For some protocol
3. So that they're ordered
**This is another form of title**

[My Data](data/test.csv)

Data 1	|Data 2	| Blank
---|---|---
1	|	2|	3	

some text and [here is possible to download the file in CSV][1]

[1]:{{ https://github.com/LizaRoger/LizaRoger.github.io }}/data/test.csv


<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/4.1.2/papaparse.js"></script>
<script>
    function arrayToTable(tableData) {
        var table = $('<table></table>');
        $(tableData).each(function (i, rowData) {
            var row = $('<tr></tr>');
            $(rowData).each(function (j, cellData) {
                row.append($('<td>'+cellData+'</td>'));
            });
            table.append(row);
        });
        return table;
    }

    $.ajax({
        type: "GET",
        url: "https://github.com/LizaRoger/LizaRoger.github.io/data/test.csv",
        success: function (data) {
            $('body').append(arrayToTable(Papa.parse(data).data));
        }
    });
</script>
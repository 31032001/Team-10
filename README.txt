SIMPLE DESIGN CRITERIA: 

        1.Developed a simple web page using  html and java script.
	2.Created graphs using chartjs API.
	3.Fetched the data from json file which is obtained from alphavantage API.
	4.Parsed the json file using simple GET http request.
	5.Labelled the price of the stock on chartjs by obtaining the data from the parsed json file.
	6.Displayed the graph,based on the user choice(daily/weekly/monthly).

METHODS USED:
	var xmlhttp = new XMLHttpRequest();
	xmlhttp.open("GET", API_call, true);
            xmlhttp.send();
            xmlhttp.onreadystatechange = function () {
                if (this.readyState == 4 && this.status == 200) {
                    var data = JSON.parse(this.responseText);
                    // console.log(data);

                    for (var key in data[period]) {
                        stockxvalues.push(key);
                        stockyvalues.push(data[period][key]['4. close']);
                    }

//holly white • Front Desk Anywhere Code Test

//initial jSON variable
var jsonFile =
	'[{"date":"2018-01-01","rate":"199.99"},{"date":"2018-01-02","rate":"199.99"},{"date":"2018-01-03","rate":"199.99"},{"date":"2018-01-04","rate":"199.99"},{"date":"2018-01-05","rate":"199.99"},{"date":"2018-01-06","rate":"115.49"},{"date":"2018-01-07","rate":"115.49"},{"date":"2018-01-08","rate":"115.49"},{"date":"2018-01-09","rate":"115.49"},{"date":"2018-01-10","rate":"115.49"},{"date":"2018-01-11","rate":"200.00"},{"date":"2018-01-15","rate":"115.49"},{"date":"2018-01-16","rate":"115.49"},{"date":"2018-01-17","rate":"115.49"},{"date":"2018-01-20","rate":"115.49"},{"date":"2018-01-21","rate":"115.49"},{"date":"2018-01-22","rate":"200.00"}]';

//convert and return json string here
var indDates = JSON.parse(jsonFile);

function makePayPeriods(indDates) {
	var finalArr = [];
	var payPeriods = {};
	//create first object in array
	firstObj = {
		'period-start': indDates[0].date,
		'current-rate': indDates[0].rate,
	};
	finalArr.push(firstObj);
	//initialize variables for for loop
	var count = 0;
	var currentRate = indDates[0].rate;
	//for loop
	for (i = 0; i < indDates.length; i++) {
		if (indDates[i].rate != currentRate) {
			currentRate = indDates[i].rate;
			count += 1;
			pStart = indDates[i].date;
			periodEnd = indDates[i - 1].date;
			repObject = { 'period-start': pStart, 'current-rate': currentRate };
			finalArr.push(repObject);
			finalArr[count - 1]['period-end'] = periodEnd;
		}
	}
	finalArr[count]['period-end'] = indDates[indDates.length - 1].date;
	return finalArr;
}

//add hex to object
function addColor(finalArr) {
	for (j = 0; j < finalArr.length; j++) {
		colorRates = finalArr[j]['current-rate'];
		var parsed = parseFloat(colorRates.replace(/\s/g, '').replace('.', ''));
		//padd according to length ;
		var hexString = '#00' + parsed.toString(16);
		finalArr[j]['hex-color'] = hexString;
	}
	return finalArr;
}

var payPeriods = makePayPeriods(indDates);
addColor(payPeriods);

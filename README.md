crowdflower.jquery.js
=======
CrowdflowerJS is a library for the crowdflower API wrapped up in javascript. The official Crowdflower API description can be found [here](http://crowdflower.com/docs-api). jQuery is required for this library to work. After the library is loaded the API is accessible via $.crowdflower.

This project is part of Web Information Systems group.

### Credits to

- Alessandro Bozzon (project conceptualization)
- Jasper Oosterman (main developer)

### TODO
- Adding and specifying gold data is not yet implemented.
- Ordering/paying of jobs is not tested yet.
- Uploading data is not yet supported from all accepted types

## CrowdflowerJS

This projects is a Javascript wrapper for web APIs exposed by CrowdFlower. Since Javascript does not allow to do cross domain requests a local proxy is required to function. A servlet that forwards the parameters and data written to the proxy and returns the response data and status is enough.

All API requests are asynchronous meaning that results (or errors) should be handled using standard .done(), .fail() and .always().

### Tutorial

(1) Load the crowdflower.jquery.js library

```javascript
<script type="text/javascript" src="../jquery.min.js"></script>
<script type="text/javascript" src="../crowdflower.jquery.js"></script>
```

(2) Setup the credentials and proxy
```javascript
var proxyURL = <url>;
var key = <key>;
$.crowdflower.key(key).proxyURL(proxyURL);
```
	
Now all the API functions are accessible in an intuitive way.
(3a) Get all the jobs 

```javascript
$.crowdflower.jobs.read().done(function(jobs) {
	//if there are jobs available
	if (jobs && jobs.length > 0) {
		for ( var i = 0; i < jobs.length; i++) {
			//process each job
		}
	}
});
```

(3b) Delete a job

```javascript
$.crowdflower.job(job_id).remove().done(function() {
	alert("Job " + job_id + " successfully deleted.")
});
```

## Function namespaces
The following table lists the namespace where functions can be found. CRUD operations are supported following the naming scheme CrowdFlower specifies in the API. The "C" is found in plural namespaces (jobs, judgments etc.) and the "RUD" are in the singular namespaces (job, judgement etc.).

<table border="1">
	<tr>
		<th>Namespace</th>
		<th>Comments</th>			
	<tr>
		<td>$.crowdflower</td>
		<td>Global functions for managing default handlers, credentials, and proxy.</td>
	</tr>
	<tr>
		<td>$.crowdflower.jobs</td>
		<td>List and create jobs</td>
	</tr>
	<tr>
		<td>$.crowdflower.job</td>
		<td>Read, update, delete a job. Delete method is named remove.</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.units</td>
		<td>List and create units</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.unit</td>
		<td>Read, update, delete a unit. Delete method is named destroy</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.judgments</td>
		<td>Create judgment.</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.judgment</td>
		<td>Read, update, delete a judgment. Delete method is named remove</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.orders</td>
		<td>Create orders</td>
	</tr>
	<tr>
		<td>$.crowdflower.job.order</td>
		<td>Read orders</td>
	</tr>
</table>


## Crowdflower behaviour
For known errors see [jCrowdFlower](https://github.com/WISDelft/crowdery-crowdflower-java/blob/master/README.md#crowdflower-behaviour).

## Organization
**Delft University of Technology** <br />
[Faculty] Electrical Engineering, Computer Science and Mathematics<br />
[Department] Web Information Systems<br />
[Contact] jasper.oosterman@gmail.com <br />

![tudelft](http://www.se.ewi.tudelft.nl/dmcd2011/images/TU-Delft_logo.gif)

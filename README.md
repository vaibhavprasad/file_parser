# file_parser

Create a web application for reading a json or an XML then provide a GUI where a user can play with the fields i.e add, remove or update fields and properties and then export the result into a JSON, CSV or XML format.

Screen1: Upload Data.
Screen2: Visualize the parsed uploaded data.
Screen3: play with visualization, add remove attributes/ properties, expand-collapse, save updated cofiguration. 
Screen4: Output in the desired format(csv, json, xml);

basic cases: 

{
	a: {
		a1: {},
		a2: {}
	},
	b: {
		b1: {},
		b2: {}
	},
	c: {
		c1: {
			c11: {}
		},
		c2: {}
	}
}

case1: data transformation in the same output format
	for instance if one wants the 2nd level of nesting i.e the expected output is [a1, a2, b1, b2 ...] then provide the Xpath for the data and iterate through the entire data and form the data.

case2: data transformation to different data format
	get the required data using x-paths, form the document and then transform it to a different format using the libraries.

The data is dependent on the access of the users. We need to map a user with a given x-path so that the user will be able to access the data on the authorized path only.

The UI should give the user a way to drag and drop the elements such that on drop the xpath of the element comes to the output and when exported, should resolve and show the data.

also there should be an option for the user to define variables where multiple fields can be added and shown as a single field in the UI. for instance let the input be as shown 

<user>
	<fname>
		vaibhav
	</fname>
	<lname>
		prasad
	</lname>
</user>

and the requested output is:

	<user>
		<fullname>vaibhav prasad</fullname>
	</user>
here the user has introduced a new attribute whose value is sum of two attributes.

***

The UI should also provide an option to localize the data. for example, amount in india is shown as 23.50. Same in europe is written as 23,50. so there should be an option in the UI to update such values again based on the x-path anf formatter.

Pages in the UI:

Page 1 will be an upload page. the user will be uploading the file and the sysyem will detect the file type. It will then parse the file and then display the items. The user can just expand/ collapse, check/ uncheck delete/ move the elements around to create the output structure. The next page will let the user export the data as per the configuration created by him in the desired format. 

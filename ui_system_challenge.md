# UI System Challenge
### [Outlier](https://outlier.ai/)
Completed by: Kristyn Bryan

<hr>

## Assignment

Your goal in this assignment is to design a front-end architecture that will support the display of the feed and expanded stories​. Your design should provide modularity, reusability, and scale efficiently with the number of stories in the feed. As part of this assignment you should also design a series of API endpoints​ to retrieve the individual elements of the story as presented in the header and expanded story (outlined below). Please note that while your design does not need to adhere strictly to a convention of any particular framework, we do use AngularJS at Outlier.

The discrete elements that will be available in a typical story include (bolded items represent values from the sample story above):

![elements - part 1](https://i.imgur.com/ymZ0kB2.png)
<br>
![elements - part 2](https://i.imgur.com/hrCGKvu.png)

<hr>

# APIs
I made the assumption that we would want to be able to search our entire database for most resources in addition to being able to search a specific company for those resources. I've created APIs to meet both of those needs, unless otherwise noted in that section.

I also assume that security and authentication details will accompany the API. Error handling and status codes will be created at well.

## Collections
`Companies`

### URLs & Methods

#### View a list of all companies
**HTTP Method**: `GET`
<br>
**URL**: `/companies`
<br>
**Status Code**: 200

#### View individual company
**HTTP Method**: `GET`
<br>
**URL**: `/companies/7`
<br>
**Status Code**: 200

#### Create a company
This will return the newly created company

**HTTP Method**: `POST`
<br>
**URL**: `/companies`
<br>
**Status Code**: 201

#### Update a company
This will return the updated company

**HTTP Method**: `PUT`
<br>
**URL**: `/companies/7`
<br>
**Status Code**: 200

#### Delete a company
This will delete the company from the database.

**HTTP Method**: `DELETE`
<br>
**URL**: `/companies/7`
<br>
**Status Code**: 204
<hr>
## Date / Date Range

### All Data in Database
#### View company data by date
**HTTP Method**: `GET`
<br>
**URL**: `/companies/dates`
<br>
**Status Code**: 200

#### View individual date
**HTTP Method**: `GET`
<br>
**URL**: `/companies/dates?start=06-12-2016`
<br>
**Status Code**: 200

#### View date range
**HTTP Method**: `GET`
<br>
**URL**: `/companies/dates?start=06-12-2016&end=06-19-2016`
<br>
**Status Code**: 200

### For Individual Company
#### View company data by date
**HTTP Method**: `GET`
<br>
**URL**: `/companies/7/dates`
<br>
**Status Code**: 200

#### View individual date
**HTTP Method**: `GET`
<br>
**URL**: `/companies/7/dates?start=06-12-2016`
<br>
**Status Code**: 200

#### View date range
**HTTP Method**: `GET`
<br>
**URL**: `/companies/7/dates?start=06-12-2016&end=06-19-2016`
<br>
**Status Code**: 200
<hr>
## Story Type

### All Data in Database
#### View company data by story type
**HTTP Method**: `GET`
<br>
**URL**: `/companies/types`
<br>
**Status Code**: 200

#### View individual type
**HTTP Method**: `GET`
<br>
**URL**: `/companies/types?story=spike`
<br>
**Status Code**: 200

#### View multiple types
**HTTP Method**: `GET`
<br>
**URL**: `/companies/types?story=spike&story=new-trend`
<br>
**Status Code**: 200

### For Individual Company
#### View company data by story type
**HTTP Method**: `GET`
<br>
**URL**: `/companies/37/types`
<br>
**Status Code**: 200

#### View individual type
**HTTP Method**: `GET`
<br>
**URL**: `/companies/37/types?story=spike`
<br>
**Status Code**: 200

#### View multiple types
**HTTP Method**: `GET`
<br>
**URL**: `/companies/37/types?story=spike&story=new-trend`
<br>
**Status Code**: 200
<hr>
## Metric

### All Data in Database
#### View company data by metrics
**HTTP Method**: `GET`
<br>
**URL**: `/companies/metrics`
<br>
**Status Code**: 200

#### View individual metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/metrics?type=unique-users`
<br>
**Status Code**: 200

#### View multiple metric types
**HTTP Method**: `GET`
<br>
**URL**: `/companies/metrics?type=unique-users&type=page-views`
<br>
**Status Code**: 200

### For Individual Company
#### View company data by metrics
**HTTP Method**: `GET`
<br>
**URL**: `/companies/48/metrics`
<br>
**Status Code**: 200

#### View individual metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/48/metrics?type=unique-users`
<br>
**Status Code**: 200

#### View multiple metric types
**HTTP Method**: `GET`
<br>
**URL**: `/companies/48/metrics?type=unique-users&type=page-views`
<br>
**Status Code**: 200
<hr>
## Segment

### All Data in Database
#### View company data by segments
**HTTP Method**: `GET`
<br>
**URL**: `/companies/segments`
<br>
**Status Code**: 200

#### View individual segments
**HTTP Method**: `GET`
<br>
**URL**: `/companies/segments?referrer=twitter.com`
<br>
**Status Code**: 200

#### View multiple segment values
**HTTP Method**: `GET`
<br>
**URL**: `/companies/segments?referrer=twitter.com&website=outlier.demo.ai`
<br>
**Status Code**: 200

### For Individual Company
#### View company data by segments
**HTTP Method**: `GET`
<br>
**URL**: `/companies/65/segments`
<br>
**Status Code**: 200

#### View individual segment
**HTTP Method**: `GET`
<br>
**URL**: `/companies/65/segments?referrer=twitter.com`
<br>
**Status Code**: 200

#### View multiple segment values
**HTTP Method**: `GET`
<br>
**URL**: `/companies/65/segments?referrer=twitter.com&website=outlier.demo.ai`
<br>
**Status Code**: 200
<hr>
## Vendor

### All Data in Database
#### View company data by vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/vendors`
<br>
**Status Code**: 200

#### View individual vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/vendors?name=google-analytics`
<br>
**Status Code**: 200

#### View multiple vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/vendors?name=google-analytics&name=mixpanel`
<br>
**Status Code**: 200

### For Individual Company
#### View company data by vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/vendors`
<br>
**Status Code**: 200

#### View individual vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/vendors?name=google-analytics`
<br>
**Status Code**: 200

#### View multiple vendors
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/vendors?name=google-analytics&name=mixpanel`
<br>
**Status Code**: 200
<hr>
## Metric Value

### All Data in Database
#### Search for individual metric value
**HTTP Method**: `GET`
<br>
**URL**: `/companies/metrics?metric-value=43`
<br>
**Status Code**: 200

#### View for individual metric value in a specific metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/metrics?type=unique-users&metric-value=43`
**Status Code**: 200

### Individual Company
#### View for individual metric value
**HTTP Method**: `GET`
<br>
**URL**: `/companies/123/metrics?metric-value=43`
<br>
**Status Code**: 200

#### View individual metric value in a specific metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/123/metrics?type=unique-users&metric-value=43`
**Status Code**: 200
<hr>
## Percentage Change
I assumed that we would not want to see the percentage change against all data in the database, but rather just individual company information.

### Individual Company
#### View daily percentage change for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/percentage-change/daily?date=06-01-2016/metrics?type=unique-users`
<br>
**Status Code**: 200

#### View weekly percentage change for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/percentage-change/weekly?start=06-01-2016&end=06-08-2016/metrics?type=unique-users`
<br>
**Status Code**: 200

NOTE: Could just do a start date for the week instead of a start and end date.
<hr>
## Population Impacted
I assumed that we would not want to see the percentage change against all data in the database, but rather just individual company information.

### Individual Company
#### View daily population impacted for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/population-impacted/daily?date=06-01-2016/metrics?type=unique-users`
<br>
**Status Code**: 200

#### View weekly population impacted for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/population-impacted/weekly?start=06-01-2016&end=06-08-2016/metrics?type=unique-users`
<br>
**Status Code**: 200
<hr>
## Last Occurrence

### Individual Company
#### View daily last occurrence for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/last-occurrence/daily?date=06-01-2016/metrics?type=unique-users`
<br>
**Status Code**: 200

#### View weekly last occurrence for metric
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/last-occurrence/weekly?start=06-01-2016&end=06-08-2016/metrics?type=unique-users`
<br>
**Status Code**: 200
<hr>
## Chart

### Individual Company
I am assuming that there is a default range of data that we display (ex: 1 year from current date of story).

#### View chart for metric / segment combination
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/chart/segments?referrer=twitter.com&website=outlier.demo.ai/metrics?type=unique-users`
<br>
**Status Code**: 200
<hr>
## Stories

#### View weekly stories
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/stories/weekly?start=06-01-2016&end=06-08-2016`
<br>
**Status Code**: 200

#### View daily stories
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/stories/daily?date=06-01-2016`
<br>
**Status Code**: 200

#### View specific story
**HTTP Method**: `GET`
<br>
**URL**: `/companies/145/stories/daily?date=06-01-2016/metrics?type=unique-users`
<br>
**Status Code**: 200

<hr>

## Database
* SQL / Postgres

## Technologies
* HTML
* CSS / SASS
* JS / AngularJS
* Mocha / Karma (Testing)
* Node (package management (NPM) - Nodemon / Grunt / Gulp)
* Angular UI (for Angular-friendly frameworks - Bootstrap, Google Maps, Chart, Date, UI-Router)
* Angular Material
* Github (version control / issue tracking)
* Slack (team communication / Github integration)
* Atom (with linters for easy debugging / style enforcement)

## Specifications
* Device specification & resolution - laptop / desktop (1024×768)
* OS / Browsers - Safari, Chrome, Opera latest (IE?)
* SEO / Marketing

## Platforms
* Development - Node.js running locally
* Staging & production - Node.js running on AWS

## User Analytics Tools
* Google Analytics

# Front End
* Client will be served the `index.html` and display different partials based on route.

### Feed
![feed](https://i.imgur.com/UqQOhX1.png)

* On page load, a call will be made to the server to get the data for this feed.
* The feed will contain the abbreviated story and will be listed by date and then by story type.
* Pagination - Not sure if there's a preference for front end or backend handling. When loading the feed, should we fetch more feed data than we need for that page and then render it on the front end when it's time (make an initial call for 100 feeds, show 20 at a time on the front end)?

### Story from Feed
![story from feed](https://i.imgur.com/U7iDlQ7.png)
* The abbreviated story will be a card with variables for each of the pieces of data (story type, chart, etc.). We can use this one card as many times as needed in the feed.
* When a user clicks on the abbreviated story, the card will expand to display the expanded story.

### Expanded Story
![expanded story](https://i.imgur.com/HRqX7LQ.png)
* When the card is expanded, a call will be made to fetch data for this story.
* The expanded story will be a top-level card that consists of 4 sections:

  1. Paragraph of details that includes variables where the data for that view can be displayed.
  2. Chart (metric history)
  3. Pie graph (How many of my customers does this affect?)
  4. Line graph (Has this happened before?)

1.The paragraph gives details of the discrete elements of the story.

2.The chart shows both the expected range that Outlier predicts (area chart) and the actual metric history (line graph). The actual history is layered on top of the predicted. The x-axis shows the date for the data, the y-axis has numbers labeled for the value of the metric. If you hover on a point in the chart, a tooltip appears with the value and date. The chart has a key that shows a dark blue color for the "Unique Users", red color for "Today", green color for "Expected Range", and a button titled "Explain Expected" that will open a modal and give more details.

3.The pie graph section consists of a header "How many of my customers does this affect?". The name of the metric is displayed above the pie chart. The pie chart has a grey area that is representative of all users and a red section that represents the percentage of users affected by this metric. The percentage is displayed inside the pie chart on the corresponding slice. The number values of the pie chart are listed next to the pie chart as well.

4.The line graph section consists of a header "Has this happened before?", followed by data. The first piece of data is a sentence that can be completed by case "YES/NO, VAR times previously". Below is the line graph that shows the dates when this happened previously (denoted with white circles and the day when this happened). The final circle being "Today" which is colored red.

* The charts can be created with [Charts.js](https://www.npmjs.com/package/angular-chart.js/) or similar library.

<hr>

## Other considerations:
* If SEO is a concern with this application, we could consider using [Angular Universal](https://angular.io/guide/universal) which will render the app server-side (this could also help with page load speed).
* Should a user be able to click on the points in the graph and be able to open the expanded story for that day?

## Resources:
* [Restful URL - dates](https://stackoverflow.com/questions/9637297/proper-rest-formatted-url-with-date-ranges)
* [Restful URL - Multiple queries](https://stackoverflow.com/questions/2602043/rest-api-best-practice-how-to-accept-list-of-parameter-values-as-input)
* [AngularJS Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md)
* [Angular Best Practices](https://airbrake.io/blog/javascript/angularjs-best-practices)
* [PEAN.js](https://github.com/StetSolutions/pean) - PostgreSQL and Angular package for quick connection for your app
* [AngularUI](https://angular-ui.github.io/)

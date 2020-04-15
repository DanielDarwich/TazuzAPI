---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - csharp: C#
  - javascript

toc_footers:
  - Request a Developer Key with ddarwichh@atid.edu.mx
  - Documentation for Maccabiah API

includes:
  - errors

search: true
---

# Introduction

Welcome to the Maccabiah API! You can use our API to access all endpoints, which can get information on sports, standings, transportation, and more in our database.

We have language bindings in C# and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

Maccabiah uses API keys to allow access to the API. You can register a new Maccabiah API key at our [developer portal](http://macabiadas.mx).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: APIKEY`

<aside class="notice">
You must replace <code>APIKEY</code> with your personal API key.
</aside>

# Maccabiah Wordpress















## Get All Posts
```csharp
static HttpClient client = new HttpClient();

public JArray GetAllPosts()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://macabiadas.mx/wp-json/wp/v2/posts");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetAllPosts();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1943,
    "date": "2018-11-01T19:46:34",
    "date_gmt": "2018-11-01T19:46:34",
    "guid": {
      "rendered": "http://macabiadas.mx/?p=1943"
    },
    "modified": "2018-11-06T17:30:41",
    "modified_gmt": "2018-11-06T17:30:41",
    "slug": "5-dias-de-tour-en-la-ciudad-de-mexico",
    "status": "publish",
    "type": "post",
    "link": "http://macabiadas.mx/2018/11/01/5-dias-de-tour-en-la-ciudad-de-mexico/",
    "title": {
      "rendered": "5 días de tour en la Ciudad de México"
    },
    "content": {
      "rendered": "",
      "protected": false
    },
    ...
  },
  
  {...}
]
```

This endpoint retrieves all posts.

### HTTP Request

`GET http://macabiadas.mx/wp-json/wp/v2/posts`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

<aside class="warning">
Remember — an APIKEY is needed to get a return value!
</aside>















## Get a Specific Post

```csharp
static HttpClient client = new HttpClient();

public JObject GetPost()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://macabiadas.mx/wp-json/wp/v2/posts/POSTID");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JObject.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JObject data = GetPost();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>POSTID</code> with a specific Post id.

> The above command returns JSON structured like this:

```json
{
  "id": 1943,
  "date": "2018-11-01T19:46:34",
  "date_gmt": "2018-11-01T19:46:34",
  "guid": {
    "rendered": "http://macabiadas.mx/?p=1943"
  },
  "modified": "2018-11-06T17:30:41",
  "modified_gmt": "2018-11-06T17:30:41",
  "slug": "5-dias-de-tour-en-la-ciudad-de-mexico",
  "status": "publish",
  "type": "post",
  "link": "http://macabiadas.mx/2018/11/01/5-dias-de-tour-en-la-ciudad-de-mexico/",
  "title": {
    "rendered": "5 días de tour en la Ciudad de México"
  },
  "content": {
    "rendered": "",
    "protected": false
  },
  "excerpt": {
    "rendered": "",
    "protected": false
  },
  "author": 2,
  "featured_media": 1605,
  "comment_status": "open",
  "ping_status": "open",
  "sticky": false,
  "template": "",
  "format": "standard",
  "meta": [],
  "categories": [
    29
  ],
  "tags": [
    62,
    65,
    64,
    63,
    60
  ],
  "jetpack_featured_media_url": "http://macabiadas.mx/wp-content/uploads/2018/10/Centro-2.jpg",
  "_links": {
    "self": [
      {
        "href": "http://macabiadas.mx/wp-json/wp/v2/posts/1943"
      }
    ],
    ...
  }
}
```

This endpoint retrieves a specific post.

<aside class="warning">You need to have the specific <code>POSTID</code> in order to make this request.</aside>

### HTTP Request

`GET http://macabiadas.mx/wp-json/wp/v2/posts/<POSTID>`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
POSTID | Integer | The ID of the post you want to retrieve.
















## Get All Tags

```csharp
static HttpClient client = new HttpClient();

public JArray GetAllTags()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://macabiadas.mx/wp-json/wp/v2/tags");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetAllTags();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 9,
    "count": 0,
    "description": "",
    "link": "http://macabiadas.mx/tag/about/",
    "name": "About",
    "slug": "about",
    "taxonomy": "post_tag",
    "meta": [],
    "_links": {
      "self": [
        {
          "href": "http://macabiadas.mx/wp-json/wp/v2/tags/9"
        }
      ],
      ...
    }
  },
  {
    "id": 52,
    "count": 1,
    "description": "",
    "link": "http://macabiadas.mx/tag/agua/",
    "name": "agua",
    "slug": "agua",
    "taxonomy": "post_tag",
    "meta": [],
    "_links": {
      "self": [
        {
          "href": "http://macabiadas.mx/wp-json/wp/v2/tags/52"
        }
      ],
      ...
    }
  },
  {...}
]
```

This endpoint gets every available tag.

### HTTP Request

`GET http://macabiadas.mx/wp-json/wp/v2/tags`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.















## Filter Posts by Tags

```csharp
static HttpClient client = new HttpClient();

public JArray GetPostsWithTag()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://macabiadas.mx/wp-json/wp/v2/posts?tags=TAG");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetPostsWithTag();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>TAG</code> with a specific Tag id.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1943,
    "date": "2018-11-01T19:46:34",
    "date_gmt": "2018-11-01T19:46:34",
    "guid": {
      "rendered": "http://macabiadas.mx/?p=1943"
    },
    "modified": "2018-11-06T17:30:41",
    "modified_gmt": "2018-11-06T17:30:41",
    "slug": "5-dias-de-tour-en-la-ciudad-de-mexico",
    "status": "publish",
    "type": "post",
    "link": "http://macabiadas.mx/2018/11/01/5-dias-de-tour-en-la-ciudad-de-mexico/",
    "title": {
      "rendered": "5 días de tour en la Ciudad de México"
    },
    "content": {
      "rendered": "",
      "protected": false
    },
    "excerpt": {
      "rendered": "",
      "protected": false
    },
    "author": 2,
    "featured_media": 1605,
    "comment_status": "open",
    "ping_status": "open",
    "sticky": false,
    "template": "",
    "format": "standard",
    "meta": [],
    "categories": [
      29
    ],
    "tags": [
      62,
      65,
      64,
      63,
      60,
      61,
      58,
      57,
      66,
      33,
      59
    ],
    ...
  },
  {...}
]
```

This endpoint retrieves all posts with a specific tag/s.

### HTTP Request

To get all available tags go to <a href="http://localhost:4567/?csharp#get-all-tags">Get All Tags</a>.

`GET http://macabiadas.mx/wp-json/wp/v2/posts?tags=TAG`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
TAG | Integer | The ID of the tag you want to filter posts by. You can use more than 1 tag by separating them with commas. Example: `http://macabiadas.mx/wp-json/wp/v2/posts?tags=62,52`
















## Get Sport Information

```csharp
static HttpClient client = new HttpClient();

public JArray GetSportInfo()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://macabiadas.mx/wp-json/wp/v2/posts?slug=SPORT");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetSportInfo();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>SPORT</code> with a specific sport name as listed on the left.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1623,
    "date": "2018-10-19T19:52:11",
    "date_gmt": "2018-10-19T19:52:11",
    "guid": {
      "rendered": "http://macabiadas.mx/?p=1623"
    },
    "modified": "2018-10-19T19:52:11",
    "modified_gmt": "2018-10-19T19:52:11",
    "slug": "futsal",
    "status": "publish",
    "type": "post",
    "link": "http://macabiadas.mx/2018/10/19/futsal/",
    "title": {
      "rendered": "Futsal"
    },
    "content": {
      "rendered": "",
      "protected": false
    },
    "excerpt": {
      "rendered": "",
      "protected": false
    },
    "author": 2,
    "featured_media": 1628,
    "comment_status": "open",
    "ping_status": "open",
    "sticky": false,
    "template": "",
    "format": "standard",
    "meta": [],
    "categories": [
      18
    ],
    "tags": [
      38,
      43,
      42,
      41,
      37,
      40,
      39
    ],
    ...
    }
  }
]
```

This endpoint retrieves a post with information from a specific sport.

### HTTP Request

`GET http://macabiadas.mx/wp-json/wp/v2/posts?slug=SPORT`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
SPORT | String | The name of the sport you want information from. Its value can be any of the following: `Aguas-Abiertas`, `Ajedréz`, `Basquetbol`, `Ciclismo`, `Equitación`, `Fútbol-Soccer`, `Futsal`, `Gimnasia-Olímpica`, `Gimnasia-Ritmica`, `Golf`, `Hockey-Pasto`, `Karate`, `Macabiman`, `Triatlón`, `Medio-Maratón`, `Natación`, `Paddel`, `Squash`, `Softball`, `Tenis`, `Tenis-de-Mesa`, `Tiro-con-Arco`, `Voleyball`, `Voleyball-de-Playa`, `WaterPolo`

















# Maccabiah Backend
















## Get All Countries Data

```csharp
static HttpClient client = new HttpClient();

public JArray GetCountriesData()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/countries");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetCountriesData();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
	"country": "Mexico",
	"flag-image-url": "http://FLAGIMAGEURL.png"
  },
  {
  	"id": 2,
  	"country": "Australia",
  	"flag-image-url": "http://FLAGIMAGEURL.png"
  }
  {...}
]
```

This endpoint retrieves information of all countries participating containing the sports they participate in.

### HTTP Request

`GET http://jmp2019.com/api/v1/countries`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.
















## Get All Country/Sports Data

```csharp
static HttpClient client = new HttpClient();

public JArray GetCountrySportsData()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/COUNTRY");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetCountrySportsData();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>COUNTRY</code> with a specific country name.

> The above command returns JSON structured like this:

```json
[
  {
  	"id": 5,
  	"name": "Swimming",
  	"sports-logo-url": "http://SPORTSLOGOURL.png",
  	"players": [
      {
      	"id": 2560,
		"Name": "John Doe",
		"player-image-url": "http://PLAYERIMAGEURL.png",
		"Birth Date": "15/10/2001",
		"Nationality": "Mexico",
		"Height": 1.85,
		"Category": "Junior",
		"Competitions": ["500 meter Backstroke", "100 meter Freestyle", "200 meter Breaststroke"],
		"Gold Medals": 0,
		"Silver Medals": 2,
		"Bronze Medals": 1
      },
      {...}
  	]
  },
  {
  	"id": 8,
  	"name": "Basketball",
  	"sports-logo-url": "http://SPORTSLOGOURL.png",
  	"players": [
      {
      	"id": 2315,
		"Name": "Jane Doe",
		"player-image-url": "http://PLAYERIMAGEURL.png",
		"Birth Date": "08/05/1997",
		"Nationality": "Mexico",
		"Height": 1.92,
		"Category": "Open",
		"Position": "Point Guard",
		"Points": 20
      },
      {...}
  	]
  },
  {...}
]
```

This endpoint retrieves information of all players that participate in each sport for a certain country.

### HTTP Request

`GET http://jmp2019.com/api/v1/COUNTRY`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
COUNTRY | String | The name of the country you want information from. If the country contains two words separate them with: <code>-</code>

<aside class="notice">Note: Player Keys and Values may vary depending on the sport.</aside>
















## Get All Sports Data

```csharp
static HttpClient client = new HttpClient();

public JArray GetSportsData()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/sports");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetSportsData();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 5,
	"sport": "Swimming",
	"sports-logo-url": "http://SPORTSLOGOURL.png"
  },
  {
  	"id": 8,
  	"sport": "Basketball",
  	"sports-logo-url": "http://SPORTSLOGOURL.png"
  }
  {...}
]
```

This endpoint retrieves information of all sports in the Maccabiah containing the countries that participate in each one and the players that participate in each country.

### HTTP Request

`GET http://jmp2019.com/api/v1/sports`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

















## Get All Sport/Countries Data

```csharp
static HttpClient client = new HttpClient();

public JArray GetSportCountriesData()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/SPORT");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetSportCountriesData();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>SPORT</code> with a specific sport name as listed on the left.

> The above command returns JSON structured like this:

```json
[
  {
  	"id": 15,
  	"name": "Brazil",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"players": [
      {
      	"id": 2560,
		"Name": "John Doe",
		"player-image-url": "http://PLAYERIMAGEURL.png",
		"Birth Date": "15/10/2001",
		"Nationality": "Brazil",
		"Height": 1.85,
		"Category": "Junior",
		"Competitions": ["500 meter Backstroke", "100 meter Freestyle", "200 meter Breaststroke"],
		"Gold Medals": 0,
		"Silver Medals": 2,
		"Bronze Medals": 1
      },
      {...}
  	]
  },
  {
  	"id": 13,
  	"name": "Chile",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"players": [
      {
      	"id": 3561,
		"Name": "Jane Doe",
		"player-image-url": "http://PLAYERIMAGEURL.png",
		"Birth Date": "08/05/1997",
		"Nationality": "Chile",
		"Height": 1.92,
		"Category": "Open",
		"Competitions": ["300 meter Freestyle", "200 meter Breaststroke"],
		"Gold Medals": 3,
		"Silver Medals": 0,
		"Bronze Medals": 0
      },
      {...}
  	]
  },
  {...}
]
```

This endpoint retrieves information of all players that participate in each country for a certain sport.

### HTTP Request

`GET http://jmp2019.com/api/v1/SPORT`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
SPORT | String | The name of the sport you want the standings of. Its value can be any of the following: `Open-Waters`, `Chess`, `Basketball`, `Cycling`, `Horse-Riding`, `Soccer`, `Futsal`, `Olimpic-Gymnastics`, `Rhythmic-Gymnastics`, `Golf`, `Field-Hockey`, `Karate`, `Macabiman`, `Triathlon`, `Half-Marathon`, `Swimming`, `Paddle`, `Squash`, `Softball`, `Tenis`, `Table-Tenis`, `Archery`, `Volleyball`, `Beach-Volleyball`, `Water-Polo`

<aside class="notice">Note: Player Keys and Values may vary depending on the sport.</aside>














## Get List of Competitions by Sport

```csharp
static HttpClient client = new HttpClient();

public JArray GetListOfCompetitions()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/SPORT/competitions");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetListOfCompetitions();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>SPORT</code> with a specific sport name as listed on the left.

> The above command returns JSON structured like this:

```json
[
  {
	"id": 256,
	"name": "500 meter Breaststroke",
	"sport": "Swimming"
  },
  {
	"id": 257,
	"name": "300 meter Freestyle",
	"sport": "Swimming"
  }
  {...}
]
```

This endpoint retrieves a list of all competitions inside a certain sport.

### HTTP Request

`GET http://jmp2019.com/api/v1/SPORT/competitions`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
SPORT | String | The name of the sport you want the standings of. Its value can be any of the following: `Open-Waters`, `Chess`, `Basketball`, `Cycling`, `Horse-Riding`, `Soccer`, `Futsal`, `Olimpic-Gymnastics`, `Rhythmic-Gymnastics`, `Golf`, `Field-Hockey`, `Karate`, `Macabiman`, `Triathlon`, `Half-Marathon`, `Swimming`, `Paddle`, `Squash`, `Softball`, `Tenis`, `Table-Tenis`, `Archery`, `Volleyball`, `Beach-Volleyball`, `Water-Polo`













## Get Standings for a Competition


```csharp
static HttpClient client = new HttpClient();

public JArray GetCompetitionStandings()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/standings/COMPETITION");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetCompetitionStandings();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>COMPETITION</code> with a specific competition name.

> The above command returns JSON structured like this:

> Swimming-300 meter Freestyle:
```json
[
  {
    "id": 155,
    "position": 1
    "name": "John Doe",
    "country-short": "CAN",
    "image-url": "http://IMAGEURL.png,
    "stats": {
		"Heat 1": "2:57",
		"Heat 2": "1:32",
		"Heat 3": "1:45",
		"Total": "6:14"
    }
  },
  {
    "id": 172,
    "position": 2
    "name": "Jane Doe",
    "country-short": "VEN",
    "image-url": "http://IMAGEURL.png,
    "stats": {
		"Heat 1": "2:41",
		"Heat 2": "2:02",
		"Heat 3": "1:55",
		"Total": "6:38"
    }
  },
  {...}
]
```

> Basketball Open:
```json
[
  {
    "id": 155,
    "position": 1
    "name": "Canada",
    "country-short": "CAN",
    "image-url": "http://IMAGEURL.png,
    "stats": {
		"W-L": "32-6",
		"%": "0.842",
		"PF": "113.5",
		"PA": "107.5"
    }
  },
  {
    "id": 172,
    "position": 2
    "name": "Venezuela",
    "country-short": "VEN",
    "image-url": "http://IMAGEURL.png,
    "stats": {
		"W-L": "20-18",
		"%": "0.526",
		"PF": "109.0",
		"PA": "109.0"
    }
  },
  {...}
]
```

This endpoint retrieves the standings of a specific competition.

### HTTP Request

`GET http://jmp2019.com/api/v1/standings/COMPETITION`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
COMPETITION | Integer | The ID of the competition you want the standings of.
















## Get All Medals by Country

```csharp
static HttpClient client = new HttpClient();

public JArray GetAllMedals()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/medals");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetAllMedals();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 5,
    "position": 1,
	"name": "Mexico",
	"flag-image-url": "http://FLAGIMAGEURL.png",
	"gold": 9,
	"silver": 12,
	"bronze" 5
  },
  {
  	"id": 8,
  	"position": 2,
  	"name": "Argentina",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 7,
	"silver": 7,
	"bronze" 0
  },
  {
  	"id": 10,
  	"position": 3,
  	"name": "Brazil",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 4,
	"silver": 9,
	"bronze" 2
  },
  {...}
]
```

This endpoint retrieves the table of all medals earned by each country in the Maccabiah sorted by most gold medals.

### HTTP Request

`GET http://jmp2019.com/api/v1/medals`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.












## Get Medals by Country on a Sport

```csharp
static HttpClient client = new HttpClient();

public JArray GetMedalsSport()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/medals/SPORT");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetMedalsSport();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>SPORT</code> with a specific sport name as listed on the left.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 5,
    "position": 1,
	"name": "Mexico",
	"flag-image-url": "http://FLAGIMAGEURL.png",
	"gold": 9,
	"silver": 12,
	"bronze" 5
  },
  {
  	"id": 8,
  	"position": 2,
  	"name": "Argentina",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 7,
	"silver": 7,
	"bronze" 0
  },
  {
  	"id": 10,
  	"position": 3,
  	"name": "Brazil",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 4,
	"silver": 9,
	"bronze" 2
  },
  {...}
]
```

This endpoint retrieves the table of all medals earned by each country in the Maccabiah sorted by most gold medals filtered by a specific sport.

### HTTP Request

`GET http://jmp2019.com/api/v1/medals/SPORT`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
SPORT | String | The name of the sport you want the medals of. Its value can be any of the following: `Open-Waters`, `Chess`, `Basketball`, `Cycling`, `Horse-Riding`, `Soccer`, `Futsal`, `Olimpic-Gymnastics`, `Rhythmic-Gymnastics`, `Golf`, `Field-Hockey`, `Karate`, `Macabiman`, `Triathlon`, `Half-Marathon`, `Swimming`, `Paddle`, `Squash`, `Softball`, `Tenis`, `Table-Tenis`, `Archery`, `Volleyball`, `Beach-Volleyball`, `Water-Polo`











## Get Medals by Sport on a Country

```csharp
static HttpClient client = new HttpClient();

public JArray GetMedalsCountry()
{
    HttpWebRequest response = (HttpWebRequest)WebRequest.Create("http://jmp2019.com/api/v1/medals/COUNTRY");

    response.UseDefaultCredentials = true;
    response.Headers.Add("Authorization", "APIKEY");

    HttpWebResponse answer = (HttpWebResponse)response.GetResponse();
    
    if (answer.StatusCode == HttpStatusCode.OK)
    {
        Stream value = answer.GetResponseStream();
        StreamReader _value = new StreamReader(value);
        if (value == null)
        {
            Console.WriteLine("Api Value Is Null");
        }

        var data = JArray.Parse(_value.ReadToEnd());
        return data;
    }
    return null;
}

JArray data = GetMedalsCountry();
```

```javascript

```

> You must replace <code>APIKEY</code> with your personal API key.

> You must replace <code>COUNTRY</code> with a specific country name.

> The above command returns JSON structured like this:

```json
[
  {
    "id": 5,
    "position": 1,
	"name": "Swimming",
	"flag-image-url": "http://FLAGIMAGEURL.png",
	"gold": 9,
	"silver": 12,
	"bronze" 5
  },
  {
  	"id": 8,
  	"position": 2,
  	"name": "Golf",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 7,
	"silver": 7,
	"bronze" 0
  },
  {
  	"id": 10,
  	"position": 3,
  	"name": "Volleyball",
  	"flag-image-url": "http://FLAGIMAGEURL.png",
  	"gold": 4,
	"silver": 9,
	"bronze" 2
  },
  {...}
]
```

This endpoint retrieves the table of all medals earned on different sports by a country in the Maccabiah sorted by most gold medals.

### HTTP Request

`GET http://jmp2019.com/api/v1/medals/COUNTRY`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
COUNTRY | String | The name of the country you want the medals of.








## Get All Schedule and Results

This endpoint retrieves the events of all the Maccabiah sorted by day.


## Get All Schedule and Results by Country

This endpoint retrieves the events of all the Maccabiah sorted by day for a specific country.

### HTTP Request

`GET http://jmp2019.com/api/v1/events/COUNTRY`

### Query Headers

Header | Default | Description
--------- | ------- | -----------
Authorization | null | You need to insert your APIKEY to get results.

### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
COUNTRY | String | The name of the country you want the events from.

## Get Schedule and Results by Sport

## Get All Venues

## Get Live Streams Data

## Athlete Central

## Partners And Sponsors

## Contact


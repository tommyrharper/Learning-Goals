# Gatsby

Install globally
```
npm i -g gatsby-cli
```
Then create a new gatsby application:
```
gatsby new gatsby_app_name
```
Then
```
cd gatsby_app_name
code .
```
Run the server with
```
gatsby develop
```

In order to create a new page all we need to do is create a new functional based component in a file in the pages section.

This can be done with ```rfc``` tab.

```JavaScript
import React from 'react'

export default function about() {
  return (
    <div>
      
    </div>
  )
}
```
Change to the following if you wanted to create 'AboutPage':
```JavaScript
import React from 'react'

const AboutPage = () => {
  return (
    <div>
      <h1>About Us</h1>
      <p>This is some information about us</p>
    </div>
  )
}

export default AboutPage
```

Then if you go to ```localhost:3000/about```, there it is!

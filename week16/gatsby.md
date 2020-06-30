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

## Installing Gatsby plugins

1. Gatsby source filesystem ---> Allows us to work with data from computers filesystem
2. Gatsby-transformer-remark ---> Convert Markdown to HTML
3. Gatsby plugin catch links ---> Intercept local links for markdown and does a clintside push state to stop the browser having to refresh the page.
```
npm i gatsby-source-filesystem gatsby-transformer-remark gatsby-plugin-catch-links
```

After installing these we need to configure them:

In ```gatsby-config.js```:
```javascript
module.exports = {
  siteMetadata: {
    title: `Gatsby Crash Course`,
    description: `Kick off your next, great Gatsby project with this default starter. This barebones starter ships with the main Gatsby configuration files you might need.`,
    author: `@gatsbyjs`,
  },
  plugins: [
    // Add in this code here
    `gatsby-plugin-react-helmet`,
    `gatsby-plugin-catch-links`,
    {
      resolve: `gatsby-source-filesystem`,
      options: {
        name: `pages`,
        path: `${__dirname}/src/pages`,
      },
    },
    `gatsby-transformer-remark`,
  ],
}
```

Now got to ```localhost:8000/___graphql``` and run the following query:

Try running the following request:

```graphql
{
  allFile {
    edges {
      node {
        id
        absolutePath
      }
    }
  }
}
```
This should show you your files.

Now try this request:

```graphql
{
  allMarkdownRemark {
    edges {
      node {
        frontmatter {
          path
          title
          date
          author
        }
        excerpt
      }
    }
  }
}

```

Here you should be able to see the markdown files in your ```./src/pages``` folder.


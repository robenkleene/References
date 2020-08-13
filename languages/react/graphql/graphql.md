# React GraphQL

## Query

An example of querying for the site metadata description:

    export const query = graphql`
    query HomePageQuery {
        site {
        siteMetadata {
            description
        }
        }
    }
    `

An example retrieving a specific item:

    query MyQuery {
      allMarkdownRemark(filter: {frontmatter: {title: {eq: "About"}}}) {
        edges {
          node {
            id
            rawMarkdownBody
          }
        }
      }
    }

## Components

An example of accessing that data in a component:

    const HomePage = () => {
    const HomePage = ({data}) => {
        return (
            <div>
            Hello!
            {data.site.siteMetadata.description}
            </div>
        )
    }

`set.siteMetadata.description` is exactly where the data is in the hierarchy in the GraphiQL browser.
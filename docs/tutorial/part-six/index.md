---
title: ટ્રાન્સફોર્મર plugins
typora-copy-images-to: ./
disableTableOfContents: true
---

> આ ટ્યુટોરીયલ Gatsby ડેટા સ્તર વિશેની શ્રેણીનો ભાગ છે. અહીં ચાલુ રાખતા પહેલા ખાતરી કરો કે [ભાગ ૪](/tutorial/part-four/) અને [ભાગ ૫](/tutorial/part-five/) પૂર્ણ કર્યો છે .

## આ ટ્યુટોરિયલમાં શું છે?

અગાઉના ટ્યુટોરીયલ કેવી રીતે સ્રોત માહિતી _લાવવા_ plugins દર્શાવ્યું કે Gatsby ડેટા સિસ્ટમ છે. આ ટ્યુટોરીયલ માં, તમે જાણશો કે કેવી રીતે ટ્રાન્સફોર્મર plugins _પરિવર્તન_ કાચા સામગ્રી સ્રોત plugins દ્વારા લાવવામાં આવ્યા હતા. સોર્સ પ્લગિન્સ અને ટ્રાન્સફોર્મર પ્લગઇન્સનું સંયોજન Gatsby સાઇટ બનાવતી વખતે તમને જોઈતી બધી માહિતી સોર્સિંગ અને ડેટા ટ્રાન્સફોર્મેશનને નિયંત્રિત કરી શકે છે.
## ટ્રાન્સફોર્મર plugins

મોટે ભાગે, તમે સ્રોત પ્લગિન્સમાંથી મેળવેલા ડેટાનું ફોર્મેટ તે નથી જે તમે તમારી વેબસાઇટ બનાવવા માટે ઉપયોગ કરવા માંગો છો. ફાઇલસિસ્ટમ સ્રોત પ્લગઇન તમને ફાઇલો _વિશે_ ડેટા ક્વેરી કરવા દે છે પરંતુ જો તમે ફાઇલોની _અંદર_ ડેટાને ક્વેરી કરવા માંગતા હોવ તો ?

આ શક્ય બનાવવા માટે, Gatsby ટ્રાન્સફોર્મર plugins સપોર્ટ કરે છે જે સ્રોત પ્લગિન્સમાંથી કાચી સામગ્રી લે છે
અને તેને વધુ ઉપયોગી રૂપે _રૂપાંતરિત_ કરે છે .

ઉદાહરણ તરીકે, માર્કડાઉન ફાઇલો. માર્કડાઉન લખવામાં સરસ છે પરંતુ જ્યારે તમે તેની સાથે પૃષ્ઠ બનાવો ત્યારે, તમારે માર્કડાઉન HTML હોવું જરૂરી છે.

તમારી સાઇટ પર એક માર્કડાઉન ફાઇલ ઉમેરો
`src/pages/sweet-pandas-eating-sweets.md` (આ તમારી પ્રથમ માર્કડાઉન બ્લોગ પોસ્ટ બનશે)
અને ટ્રાન્સફોર્મર plugins અને ગ્રાફક્યુએલનો ઉપયોગ કરીને તેને HTML માં કેવી રીતે રૂપાંતરિત કરવું તે શીખો .

```markdown:title=src/pages/sweet-pandas-eating-sweets.md
---
title: "Sweet Pandas Eating Sweets"
date: "2017-08-10"
---

Pandas are really sweet.

Here's a video of a panda eating sweets.

<iframe width="560" height="315" src="https://www.youtube.com/embed/4n0xNbfJLR8" frameborder="0" allowfullscreen></iframe>
```

એકવાર તમે ફાઇલને સાચવો, પછી `/my-files/` ફરી જુઓ — નવી માર્કડાઉન ફાઇલ કોષ્ટકમાં છે. આ ગેટ્સબીની ખૂબ શક્તિશાળી સુવિધા છે.
પહેલાનાં `siteMetadata` ઉદાહરણની જેમ , source plugins ડેટાને જીવંત-ફરીથી લોડ કરી શકે છે.
`gatsby-source-filesystem` વી ફાઇલો ઉમેરવા માટે હંમેશાં સ્કેન કરે છે અને જ્યારે તેઓ હોય, ત્યારે તમારી ક્વેરીઝ ફરીથી ચલાવે છે.

એક ટ્રાન્સફોર્મર પ્લગઇન ઉમેરો જે માર્કડાઉન ફાઇલોને રૂપાંતરિત કરી શકે છે:

```shell
npm install --save gatsby-transformer-remark
```

પછી સામાન્ય રીતે gatsby-config.js ઉમેરો:

```javascript:title=gatsby-config.js
module.exports = {
  siteMetadata: {
    title: `Pandas Eating Lots`,
  },
  plugins: [
    {
      resolve: `gatsby-source-filesystem`,
      options: {
        name: `src`,
        path: `${__dirname}/src/`,
      },
    },
    `gatsby-transformer-remark`, // highlight-line
    `gatsby-plugin-emotion`,
    {
      resolve: `gatsby-plugin-typography`,
      options: {
        pathToConfigModule: `src/utils/typography`,
      },
    },
  ],
}
```

ડેવલપમેન્ટ સર્વર ફરીથી પ્રારંભ કરો પછી તાજું કરો (અથવા ફરીથી ખોલો) GraphQL અને સ્વત: પૂર્ણ જુઓ:

![markdown-autocomplete](markdown-autocomplete.png)

`allMarkdownRemark` ફરીથી પસંદ કરો અને તેને જેમ ચલાવો તેમ ચલાવો `allFile`.
તમે તાજેતરમાં ઉમેર્યું તે માર્કડાઉન ફાઇલ તમે ત્યાં જોશો. `MarkdownRemark` નોડ પર ઉપલબ્ધ ક્ષેત્રોનું અન્વેષણ કરો .

![markdown-query](markdown-query.png)

બરાબર! આસ્થાપૂર્વક, કેટલીક મૂળભૂત જગ્યાએ આવવાનું શરૂ થઈ ગયું છે. ડેટાને _લાવવા_ સોર્સ plugins કે Gatsby ડેટા સિસ્ટમ અને _ટ્રાન્સફોર્મર_ plugins કાચા સામગ્રી સ્રોત plugins દ્વારા લાવવામાં પરિવર્તન. આ પેટર્ન Gatsby સાઇટ બનાવતી વખતે તમને જોઈતી બધી ડેટા સોર્સિંગ અને ડેટા ટ્રાન્સફોર્મેશનને હેન્ડલ કરી શકે છે.
## માં તમારી સાઇટની માર્કડાઉન ફાઇલોની સૂચિ બનાવો `src/pages/index.js`

હવે તમારે આગળનાં પૃષ્ઠ પર તમારી માર્કડાઉન ફાઇલોની સૂચિ બનાવવી પડશે. ઘણા બ્લોગ્સની જેમ,
તમે દરેક બ્લ બ્લોગ પોસ્ટને પોઇન્ટ કરીને આગળના પૃષ્ઠ પરની લિંક્સની સૂચિ સાથે સમાપ્ત થવા માંગો છો.
ગ્રાફક્યુએલ દ્વારા તમે માર્કડાઉન બ્લોગ પોસ્ટ્સની વર્તમાન સૂચિ માટે _ક્વેરી_ કરી શકો છો જેથી તમારે સૂચિ જાતે જ જાળવવાની જરૂર રહેશે નહીં.

`src/pages/my-files.js` પૃષ્ઠની જેમ, `src/pages/index.js` કેટલાક પ્રારંભિક HTML અને સ્ટાઇલ સાથે ગ્રાફક્યુએલ ક્વેરી ઉમેરવા માટે નીચેની સાથે બદલો .

```jsx:title=src/pages/index.js
import React from "react"
import { graphql } from "gatsby"
import { css } from "@emotion/core"
import { rhythm } from "../utils/typography"
import Layout from "../components/layout"

export default ({ data }) => {
  console.log(data)
  return (
    <Layout>
      <div>
        <h1
          css={css`
            display: inline-block;
            border-bottom: 1px solid;
          `}
        >
          Amazing Pandas Eating Things
        </h1>
        <h4>{data.allMarkdownRemark.totalCount} Posts</h4>
        {data.allMarkdownRemark.edges.map(({ node }) => (
          <div key={node.id}>
            <h3
              css={css`
                margin-bottom: ${rhythm(1 / 4)};
              `}
            >
              {node.frontmatter.title}{" "}
              <span
                css={css`
                  color: #bbb;
                `}
              >
                — {node.frontmatter.date}
              </span>
            </h3>
            <p>{node.excerpt}</p>
          </div>
        ))}
      </div>
    </Layout>
  )
}

export const query = graphql`
  query {
    allMarkdownRemark {
      totalCount
      edges {
        node {
          id
          frontmatter {
            title
            date(formatString: "DD MMMM, YYYY")
          }
          excerpt
        }
      }
    }
  }
`
```

હવે ફ્રોન્ટપેજ આના જેવું દેખાવું જોઈએ:

![frontpage](frontpage.png)

પરંતુ તમારી એક બ્લોગ પોસ્ટ થોડી એકલા લાગે છે. તો ચાલો બીજી એક ઉમેરો
`src/pages/pandas-and-bananas.md`

```markdown:title=src/pages/pandas-and-bananas.md
---
title: "Pandas and Bananas"
date: "2017-08-21"
---

Do Pandas eat bananas? Check out this short video that shows that yes! pandas do
seem to really enjoy bananas!

<iframe width="560" height="315" src="https://www.youtube.com/embed/4SZl1r2O_bY" frameborder="0" allowfullscreen></iframe>
```

![two-posts](two-posts.png)

જે સરસ લાગે છે! સિવાય… પોસ્ટ્સનો ક્રમ ખોટો છે.

પરંતુ આને ઠીક કરવું સરળ છે. જ્યારે કોઈ પ્રકારનાં કનેક્શનની પૂછપરછ કરો છો, ત્યારે તમે ગ્રાફક્યુએલ ક્વેરી પર વિવિધ દલીલો પસાર કરી શકો છો.
તમે `sort` અને `filter` ગાંઠો કરી શકો છો , કેટલા ગાંઠો પર સેટ કરવા `skip` અને `limit` કેટલા નોડ્સને પ્રાપ્ત કરવા તે પસંદ કરી શકો છો.
આ શક્તિશાળી સમૂહ ઓપરેટરો સાથે, તમે ઇચ્છો તે કોઈપણ ડેટાને પસંદ કરી શકો છો - તમને જરૂરી ફોર્મેટમાં.

તમારા ઇન્ડેક્સ પૃષ્ઠની GraphQL ક્વેરી, ફેરફાર `allMarkdownRemark` કરવા માટે
`allMarkdownRemark(sort: { fields: [frontmatter___date], order: DESC })`. _નોંધ: `frontmatter` અને `date` વચ્ચે ૩ અન્ડરસ્કોર્સ છે._
આને સાચવો અને સ ગોઠવણ ઓર્ડર ઠીક થવો જોઈએ.

GraphQL ખોલવાનો અને વિવિધ ગોઠવણ વિકલ્પો સાથે રમવાનો પ્રયાસ કરો.
તમે `allFile` અન્ય જોડાણોની સાથે જોડાણને ગોઠવણ કરી શકો છો .

અમારા ક્વેરી ઓપરેટરો વધુ દસ્તાવેજો માટે, અમારા [ગ્રાફક્યુએલ સંદર્ભ માર્ગદર્શિકાનું](/docs/graphql-reference/) અન્વેષણ કરો .

## પડકાર

બ્લોગ પોસ્ટ ધરાવતું નવું પૃષ્ઠ બનાવવાનો પ્રયાસ કરો અને જુઓ હોમપેજ પર બ્લોગ પોસ્ટ્સની સૂચિનું શું થાય છે!

## હવે પછી શું આવી રહ્યું છે?

આ મહાન છે! તમે હમણાં જ એક સરસ અનુક્રમણિકા પૃષ્ઠ બનાવ્યું છે જ્યાં તમે તમારી માર્કડાઉન ફાઇલોને ક્વેરી કરી રહ્યાં છો અને બ્લોગ પોસ્ટ શીર્ષકો અને અવતરણોની સૂચિ બનાવી રહ્યા છો. પરંતુ તમે ફક્ત અવતરણો જોવા માંગતા નથી, તમારે તમારી માર્કડાઉન ફાઇલો માટે વાસ્તવિક પૃષ્ઠો જોઈએ છે.

માં પ્રતિક્રિયા ઘટકો મૂકીને તમે પૃષ્ઠો બનાવવાનું ચાલુ રાખી શકો છો `src/pages`. જો કે, તમે પછીથી _ડેટામાંથી_ પૃષ્ઠો બનાવવાની _રીત_ શીખીશું. Gatsby છે નથી ઘણી સ્થિર સાઇટ જનરેટર જેમ ફાઇલો માંથી પૃષ્ઠો બનાવવા માટે મર્યાદિત છે. Gatsby તમને તમારા ડેટાને ક્વેરી આપવા માટે ગ્રાફક્યુઅલનો ઉપયોગ કરવા દે છે અને ક્વેરી પરિણામોને પૃષ્ઠો પર મેપ કરવા દે છે - બિલ્ડ સમયે. આ ખરેખર શક્તિશાળી વિચાર છે. તમે તેના અસર અને તે પછીના ટ્યુટોરીયલમાં તેનો ઉપયોગ કરવાની રીતો અન્વેષણ કરશો, જ્યાં તમે [ડેટાથી પૃષ્ઠો કેવી રીતે પ્રોગ્રામ બનાવવી તે શીખી શકશો](/tutorial/part-seven/).

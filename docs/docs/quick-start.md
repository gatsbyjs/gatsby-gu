---
title: ઝડપી શરૂઆત
---

આ ઝડપી શરૂઆતનો હેતુ મધ્યમ ડેવલપર થી અદ્યતન ડેવલપર માટે બનાવાયેલ છે. એક હળવી પ્રસ્તાવના માટે Gatsby, [head to our tutorial](/ટ્યુટોરિયલ/)!

## Gatsby CLI નો ઉપયોગ કરો

<EggheadEmbed
  lessonLink="https://egghead.io/lessons/gatsby-quick-start-with-gatsby-create-develop-and-build-gatsby-sites-from-the-command-line"
  lessonTitle="Gatsby સાથે ઝડપી પ્રારંભ: કમાન્ડ લાઇનથી Gatsby સાઇટ્સ બનાવો, ડેવલોપ કરો અને નિર્માણ કરો"
/>

**નોંધ**: આ વિડિઓ માં `npx` નો ઉપયોગ  થયો છે, જે npm પેકેજને પ્રથમ ઇન્સ્ટોલ કર્યા વિના ચલાવવાનું એક સાધન છે. તમારા કમ્પ્યુટર પર Gatsby-CLI સ્થાપિત કર્યા પછી કમાન્ડ `npx gatsby new` ચલાવો એ `gatsby new` ચલાવવા જેવું જ છે.

<<<<<<< HEAD
### Gatsby CLI ઇન્સટોલ કરો.
=======
### Install the Gatsby CLI
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
npm install -g gatsby-cli
```

<<<<<<< HEAD
### નવી સાઇટ બનાવો.
=======
> The above command installs Gatsby CLI globally on your machine.

### Create a new site
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
gatsby new gatsby-site
```

<<<<<<< HEAD
### ડિરેક્ટરીઓને સાઇટ ફોલ્ડરમાં બદલો.
=======
### Change directories into site folder
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
cd gatsby-site
```

<<<<<<< HEAD
### ડેવલપમેન્ટ સર્વર પ્રારંભ કરો.
=======
### Start development server
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
gatsby develop
```

<<<<<<< HEAD
Gatsby એ ડિફોલટ રૂપે `localhost:8000` ઉપયોગ કરી શકાય તેવા હોટ રિલોડીંગ ડેવલપમેન્ટ એન્વાયર્નમેન્ટ ની શરૂઆત કરશે.
=======
Gatsby will start a hot-reloading development environment accessible by default at `http://localhost:8000`.
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

`src/pages` માં જાવાસ્ક્રિપ્ટ પૃષ્ઠોને સંપાદિત કરવાનો પ્રયાસ કરો. સાચવેલ ફેરફારો બ્રાઉઝરમાં લાઇવ ફરીથી લોડ કરશે

<<<<<<< HEAD
### એક પ્રોડક્શન બિલ્ડ બનાવો.
=======
### Create a production build
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
gatsby build
```

Gatsby તમારી સાઇટ માટે ઓપ્ટિમાઇઝ પ્રોડક્શન બિલ્ડ બનાવશે, જે રૂટ દીઠ સ્ટેટીક HTML અને જાવાસ્ક્રિપ્ટ કોડ બનાવશે.

<<<<<<< HEAD
### પ્રોડક્શન બિલ્ડ ને સ્થાનિક રીતે સર્વે કરો.
=======
### Serve the production build locally
>>>>>>> 90932a06db2e297cf416552b84e48b4b82e56fbc

```shell
gatsby serve
```

Gatsby તમારી બનાવેલ સાઇટનું પરીક્ષણ કરવા માટે સ્થાનિક HTML સર્વર શરૂ કરે છે. આ આદેશનો ઉપયોગ કરતા પહેલા `gatsby build` ની મદદથી તમારી સાઇટ બનાવવાનું યાદ રાખો.

### ઍક્સેસ ડોક્યુમેન્ટશન ફોર CLI કંમાન્ડ

CLI આદેશો માટે વિગતવાર દસ્તાવેજીકરણ જોવા માટે, ટર્મિનલ મા `gatsby --help` ચલાવો.

વિશિષ્ટ કમાન્ડ માટે, `gatsby COMMAND_NAME --help` ચલાવો, ઉદાહરણ તરીકે `gatsby new --help`.

Gatsby CLI વિશે વધુ માહિતી માટે, [CLI reference](/docs/gatsby-cli/) જોવો .

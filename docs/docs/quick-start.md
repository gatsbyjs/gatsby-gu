---
title: ઝડપી શરૂઆત
---

આ ઝડપી શરૂઆતનો હેતુ મધ્યમ ડેવલપર થી અદ્યતન ડેવલપર માટે બનાવાયેલ છે. એક હળવી પ્રસ્તાવના માટે Gatsby, [head to our tutorial](/ટ્યુટોરિયલ/)!

## Gatsby CLI નો ઉપયોગ કરો

<EggheadEmbed
  lessonLink="https://egghead.io/lessons/gatsby-quick-start-with-gatsby-create-develop-and-build-gatsby-sites-from-the-command-line"
  lessonTitle="Gatsby સાથે ઝડપી પ્રારંભ: કમાન્ડ લાઇનથી Gatsby સાઇટ્સ બનાવો, ડેવલોપ કરો અને નિર્માણ કરો"
/>

**નોંધ**: આ વિડિઓ માં `npx` નો ઉપયોગ  થયો છે, જે npm પેકેજને પ્રથમ ઇન્સ્ટોલ કર્યા વિના ચલાવવાનું એક સાધન છે. તમારા કમ્પ્યુટર પર Gatsby-CLI સ્થાપિત કર્યા પછી કમાન્ડ `npx gatsby new` ચાલવો એ `gatsby new` ચાલવા જેવું જ છે.

### Gatsby CLI ઇન્સટોલ કરો.

```shell
npm install -g gatsby-cli
```

### નવી સાઇટ બનાવો.

```shell
gatsby new gatsby-site
```

### ડિરેક્ટરીઓને સાઇટ ફોલ્ડરમાં બદલો.

```shell
cd gatsby-site
```

### ડેવલપમેન્ટ સર્વર પ્રારંભ કરો.

```shell
gatsby develop
```

Gatsby એ ડિફોલટ રૂપે `localhost:8000` ઉપયોગ કરી શકાય તેવા હોટ રિલોડીંગ ડેવલપમેન્ટ એન્વાયર્નમેન્ટ ની શરૂઆત કરશે.

`src/pages` માં જાવાસ્ક્રિપ્ટ પૃષ્ઠોને સંપાદિત કરવાનો પ્રયાસ કરો. સાચવેલ ફેરફારો બ્રાઉઝરમાં લાઇવ ફરીથી લોડ કરશે

### એક પ્રોડક્શન બિલ્ડ બનાવો.

```shell
gatsby build
```

Gatsby તમારી સાઇટ માટે ઓપ્ટિમાઇઝ પ્રોડક્શન બિલ્ડ બનાવશે, જે રૂટ દીઠ સ્ટેટીક HTML અને જાવાસ્ક્રિપ્ટ કોડ બનાવશે.

### પ્રોડક્શન બિલ્ડ ને સ્થાનિક રીતે સર્વે કરો.

```shell
gatsby serve
```

Gatsby તમારી બનાવેલ સાઇટનું પરીક્ષણ કરવા માટે સ્થાનિક HTML સર્વર શરૂ કરે છે. આ આદેશનો ઉપયોગ કરતા પહેલા `gatsby build` ની મદદથી તમારી સાઇટ બનાવવાનું યાદ રાખો.

### ઍક્સેસ ડોક્યુમેન્ટશન ફોર CLI કંમાન્ડ

CLI આદેશો માટે વિગતવાર દસ્તાવેજીકરણ જોવા માટે, ટર્મિનલ મા `gatsby --help` ચલાવો.

વિશિષ્ટ કમાન્ડ માટે, `gatsby COMMAND_NAME --help` ચલાવ, ઉદાહરણ તરીકે `gatsby new --help`.

Gatsby CLI વિશે વધુ માહિતી માટે, [CLI reference](/docs/gatsby-cli/) જોવો .

---
શીર્ષક: ઝડપી શરૂઆત
---

આ ઝડપી શરૂઆતનો હેતુ મધ્યમ ડેવલપર થી અદ્યતન ડેવલપર માટે બનાવાયેલ છે. એક હળવી પ્રસ્તાવના માટે Gatsby, [head to our tutorial](/ટ્યુટોરિયલ/)!

## Gatsby CLI નો ઉપયોગ કરો

<EggheadEmbed
  lessonLink="https://egghead.io/lessons/gatsby-quick-start-with-gatsby-create-develop-and-build-gatsby-sites-from-the-command-line"
  lessonTitle="Gatsby સાથે ઝડપી પ્રારંભ: કમાન્ડ લાઇનથી Gatsby સાઇટ્સ બનાવો, ડેવલોપ કરો અને નિર્માણ કરો"
/>

**નોંધ**: આ વિડિઓ માં `npx` નો ઉપયોગ  થયો છે, જે npm પેકેજને પ્રથમ ઇન્સ્ટોલ કર્યા વિના ચલાવવાનું એક સાધન છે. તમારા કમ્પ્યુટર પર Gatsby-CLI સ્થાપિત કર્યા પછી આદેશ `npx gatsby new` ચાલવો એ `gatsby new` ચાલવા જેવું જ છે.

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

Gatsby will start a hot-reloading development environment accessible by default at `localhost:8000`.

Try editing the JavaScript pages in `src/pages`. Saved changes will live reload in the browser.

### Create a production build.

```shell
gatsby build
```

Gatsby will perform an optimized production build for your site, generating static HTML and per-route JavaScript code bundles.

### Serve the production build locally.

```shell
gatsby serve
```

Gatsby starts a local HTML server for testing your built site. Remember to build your site using `gatsby build` before using this command.

### Access documentation for CLI commands

To see detailed documentation for the CLI commands, run `gatsby --help` in the terminal.

For specific commands, run `gatsby COMMAND_NAME --help` e.g. `gatsby new --help`.

For more information on the Gatsby CLI, visit the [CLI reference](/docs/gatsby-cli/) section of the docs.

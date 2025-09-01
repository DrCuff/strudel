```bash
brew install node
git clone https://codeberg.org/uzu/strudel.git
cd strudel
brew install pnpm
pnpm i
echo "pnpm dev" > go.sh
chmod +x go.sh

jcuff@midnight strudel.git % ./go.sh

> @strudel/monorepo@0.5.0 dev /Users/jcuff/strudel/strudel.git
> npm run prestart && cd website && npm run dev
> @strudel/website@0.6.0 dev
> astro dev --host 0.0.0.0

21:21:54 [types] Generated 0ms
21:21:54 [content] Syncing content
21:21:54 [content] Synced content

 astro  v5.1.9 ready in 357 ms

┃ Local    http://localhost:4321/
```

Make music...


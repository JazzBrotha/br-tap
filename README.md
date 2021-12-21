# Example

Example project setup. Disable JavaScript in your browser to see SSR in action.

```bash
git clone git@github.com:EmilTholin/svelte-routing.git
cd svelte-routing/example
npm install
npm start
# open http://localhost:5000
```

## Deploy

Run `npm run docker:build` to build Docker container.

Deploy to Kubernetes by running `microk8s kubectl rollout restart deployment br-tap`

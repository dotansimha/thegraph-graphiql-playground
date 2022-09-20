<sub>
If you're looking for the GraphiQL repository, go to https://github.com/graphql/graphiql.
</sub>

---

# The Graph GraphiQL Playground

_Configuration, styling and extensions for the GraphiQL Playground component embedded in The Graph Protocol applications_

## Usage

Install `@edgeandnode/graphiql-playground` with your favorite package manager.

```sh
npm i @edgeandnode/graphiql-playground
```

Then, import `GraphProtocolGraphiQL` and use it in your React components.

```ts
import { GraphProtocolGraphiQL } from "./src";

const defaultQuery = `
{
  subgraphs(first: 5, orderBy: createdAt, orderDirection: desc) {
    displayName
  }
}`;

const Playground = () => {
  return (
    <GraphProtocolGraphiQL
      fetcher={{
        url: "https://api.thegraph.com/subgraphs/name/graphprotocol/graph-network-mainnet-staging",
      }}
      defaultQuery={defaultQuery}
    />
  );
};
```

## Contributing

- This library exports one React component named `GraphProtocolGraphiQL`, built using `@graphiql/react`, `@graphiql/plugin-explorer` and `@graphiql/toolkit`.
- It's meant to be used instead of [`graphiql`](https://github.com/graphql/graphiql/tree/main/packages/graphiql) package in The Graph Protocol applications.
- Install the dependencies and run scripts from [_package.json_](./package.json) using `pnpm`.

# How to reproduce

1.
```shell
cd service1
make run
```

2.
```shell
npm install -g wgc@latest
wgc router compose -i graph.yaml -o config.json
```

3. use config.json for run router

4. run query

```graphql
query Test {
    test(input: {
        filter: {
            # empty
        }
    }) {
        a
        b
    }
}
```

5. view result

```json
{
  "errors": [
    {
      "message": "Variable \"$a\" got invalid value {\"filter\":{}}; Field \"b\" of required type \"Int!\" was not provided."
    }
  ],
  "data": null
}
```
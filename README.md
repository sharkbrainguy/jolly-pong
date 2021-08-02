# Jolly Pong

An object-algebra-esque approach to typescript schemas, i.e. value-level type-definition.

```typescript
import * as J from 'jolly-pong';

const schema = <T>(alg: J.ISchemaAlgebra<T>) =>
  alg.object({
    foo: alg.array(alg.anyOf(alg.number(), alg.string())),
    bar: alg.literal(7),
  });

const example = schema(J.toValue);
export type Example = typeof example;
export const isExample = schema(J.check);
```

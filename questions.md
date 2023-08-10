Questions:

### 1. why is my count not reflecting on dom

problem:

```
const [count, setCount]= useState({
    liabilities:0, assets:0
})


```

solution:

```

const countCount = (seeds: SeedDataTemp[]) => {
    let [assetsC, liabsC] = [0, 0];
    for (let i = 0; i < seeds.length; i++) {
      if (seeds[i].amount < 0) liabsC++;
      if (seeds[i].amount > 0) assetsC++;
    }
    setCount({
      liabilities: liabsC,
      assets: assetsC
    });
  };
```

explanation:

from:

```
const countCount = () => {
    ...
}
```

to:

```

const countCount = (seeds: SeedDataTemp[]) => {
  ...
}
```

capturing the new seed data with each new fetch, rather than using an old stale copy

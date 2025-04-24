---
title: "Distance of high-dimensional normal distribution has mean √D, variance 0.7"
---

from  [[In high-dimensional space, the normal distribution is almost uniformly distributed on the hypersphere]]
Distance of high-dimensional normal distribution has mean √N, variance 0.7
- The Euclidean distance from the origin of a data point that follows a D-dimensional normal distribution $N_D(0, 1)$ roughly follows a distribution with mean $\sqrt{D}$standard deviation $1/\sqrt{2}$.
    - Not exactly [[chi-square distribution]].
    - Surprisingly small standard deviation
        - So [In high-dimensional space, the normal distribution is almost uniformly distributed on the hypersphere

![image](https://gyazo.com/0d112dd0f26b35bcdb475adc65bde59d/thumb/1000)

![image](https://gyazo.com/dcb18b69b4fa13bbea0c1f7a2568176e/thumb/1000)
:

```
mean= 9.972699059944992 sd= 0.70375223347664
mean= 19.98802691399663 sd= 0.7060739521568569
mean= 29.992667664100654 sd= 0.7078926693796469
mean= 39.99309275039724 sd= 0.7074454497781785
```


py

```
import numpy as np
import matplotlib.pyplot as plt

# of samples and number of dimensions
num_samples = 100000
dimensions = [100, 400, 900, 1600] # Example dimensions

# Plot the distribution of distances
plt.figure(figsize=(10, 6))
for d in dimensions:
    # Generate random data following a d-dimensional normal distribution
    data = np.random.normal(0, 1, (num_samples, d))
    
    # Calculate the distance of each data point from the origin
    distances = np.linalg.norm(data, axis=1)

    # Mean and variance
    print("mean=", distances.mean(), "sd=", distances.std())
    
    # Plot a histogram
    plt.hist(distances, bins=30, alpha=0.5, label=f'{d} dimensions', density=True)

# Graph setup
plt.xlabel('Distance from Origin')
plt.ylabel('Density')
plt.legend()
plt.title('Distribution of Distances from Origin in High-Dimensional Space')
plt.show()
```



---
This page is auto-translated from [/nishio/高次元正規分布の距離は平均√D, 分散0.7](https://scrapbox.io/nishio/高次元正規分布の距離は平均√D, 分散0.7) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
# random-seed

## numpy
- make numpy code replicable in multiple runs
  ```
  # set a fixed seed
  np.random.seed(42)
  ``` 
- repeat for every operation / function call the same result
  ```
  import numpy as np
  # set the seed
  np.random.seed(42)
  np.random.randint(0,100)
  > 51
  # set the seed, reset state
  np.random.seed(42)
  np.random.randint(0,100)
  > 51
  ```
- call some operation with a fixed seed without resetting state
  ```
  import numpy as np
  # set the seed
  np.random.seed(42)
  np.random.randint(0,100)
  > 51
  # save seed 42 state
  state_s42 = np.random.get_state()
  ...
  # do other stuff, change seed, ecc
  ...
  # set seed 42 state
  np.random.set_state(state_s42)
  np.random.randint(0,100)
  > 92
  ```
  this is the same as :
  ```
  import numpy as np
  np.random.seed(42)
  np.random.randint(0,100)
  > 51
  np.random.randint(0,100)
  > 92

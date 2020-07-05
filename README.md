# Guli
The package wrote by [Itai Gu](https://github.com/itaiguli/)

# With the package you can

Guli can be used between different Python scripts & between many processes or at the same script.
pass variables between main Process and another (Multiprocess) Process.
  - Pass variables between different Python scripts.
  - Pass variables between 'Main Process' and another (Multiprocess) Process.
  - Use variables at the same script.
  - Create / Delete / Edit  -  GuliVariables.

Guli is open source with a [public repository](https://github.com/itaiguli/guli/) on GitHub.

### Installation

Install Guli from PIP.

```sh
$ pip install guli
```

Guli doesn't require installing any additional PIP package.

### Examples

Guli can be used between different Python scripts & between many processes or at the same script.

This will pass variables between main Process and another (Multiprocess) Process.

```python
import guli
import multiprocessing

string = guli.GuliVariable("hello").get()
print(string) # returns empty string ""

def my_function():
  ''' change the value from another process '''
  guli.GuliVariable("hello").setValue(4)

multiprocessing.Process(target=my_function).start()

import time
time.sleep(0.01) # delay after process to catch the update


string = guli.GuliVariable("hello").get()
print(string) # returns "success!!!"
```

License
----

MIT

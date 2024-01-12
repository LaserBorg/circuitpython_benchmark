# circuitpython benchmark

Raspberry Pi Pico (RP2040), Adafruit Metro M7 (NXP IMXRT10XX) and Intel i7 CPU benchmark.

## abstract
Script for Python and CircuitPython measures computation time, covering:
- int and float datatypes
- vectorized vs. looped operations 
- arithmetic, algebraic and trigonometric operations.


## results

|<br> datatype|<br>operation| **Raspberry Pi Pico**<br>t (s)|  |**Adafruit Metro M7**<br>t (s)| <br>vs. Pico|  | **Intel i7-6700HQ Laptop** <br>t (s)| <br> vs. Pico |
|----------------:|------------:|------------:|---------:|----------------------:|---------:|-----:|---------------------:|---------:|
|                 |             |             |          |                       |          |      |                      |          |
| int             | bitshift    | 31.614      |          | 6.710                 | 4.7 x    |      | 0.164                | 192.5 x  |
|                 |             |             |          |                       |          |      |                      |          |
| int             | modulo      | 12.077      |          | 2.404                 | 5.0 x    |      | 0.147                | 82.0 x   |
| int             | bitwise-and | 11.597      |          | 2.313                 | 5.0 x    |      | 0.145                | 80.1 x   |
| int             | bitwise-or  | 11.596      |          | 2.314                 | 5.0 x    |      | 0.152                | 76.5 x   |
| int             | bitwise-xor | 11.598      |          | 2.312                 | 5.0 x    |      | 0.152                | 76.4 x   |
|                 |             |             |          |                       |          |      |                      |          |
| int             | add         | 19.694      |          | 4.051                 | 4.9 x    |      | 0.152                | 129.2 x  |
| float           | add         | 13.319      |          | 2.629                 | 5.1 x    |      | 0.127                | 105.1 x  |
| array(np.float) | add         | 1.561       |          | 0.183                 | 8.5 x    |      | 0.006                | 248.7 x  |
| vec speedup     |             | 8.5 x       |          | 14.4 x                |          |      | 20.2 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| int             | sub         | 11.597      |          | 2.313                 | 5.0 x    |      | 0.147                | 79.1 x   |
| float           | sub         | 13.566      |          | 2.633                 | 5.2 x    |      | 0.132                | 102.5 x  |
| array(np.float) | sub         | 1.754       |          | 0.179                 | 9.8 x    |      | 0.006                | 272.3 x  |
| vec speedup     |             | 7.7 x       |          | 14.7 x                |          |      | 20.5 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| int             | mul         | 34.808      |          | 6.549                 | 5.3 x    |      | 0.144                | 241.6 x  |
| float           | mul         | 13.383      |          | 2.639                 | 5.1 x    |      | 0.135                | 98.9 x   |
| array(np.float) | mul         | 1.890       |          | 0.204                 | 9.3 x    |      | 0.006                | 311.1 x  |
| vec speedup     |             | 7.1 x       |          | 12.9 x                |          |      | 22.3 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| int             | div         | 13.549      |          | 2.381                 | 5.7 x    |      | 0.138                | 97.9 x   |
| float           | div         | 13.991      |          | 2.692                 | 5.2 x    |      | 0.125                | 111.5 x  |
| array(np.float) | div         | 2.097       |          | 0.238                 | 8.8 x    |      | 0.006                | 340.9 x  |
| vec speedup     |             | 6.7 x       |          | 11.3 x                |          |      | 20.4 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| int             | exp         | 20.625      |          | 3.221                 | 6.4 x    |      | 0.297                | 69.4 x   |
| float           | exp         | 20.457      |          | 3.547                 | 5.8 x    |      | 0.285                | 71.7 x   |
| array(np.float) | exp         | 6.627       |          | 0.510                 | 13.0 x   |      | 0.012                | 548.1 x  |
| vec speedup     |             | 3.1 x       |          | 7.0 x                 |          |      | 23.6 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| int             | sqr         | 17.391      |          | 3.241                 | 5.4 x    |      | 0.288                | 60.4 x   |
| float           | sqr         | 17.134      |          | 3.301                 | 5.2 x    |      | 0.276                | 62.2 x   |
| array(np.float) | sqr         | 2.844       |          | 1.017                 | 2.8 x    |      | 0.006                | 445.9 x  |
| vec speedup     |             | 6.0 x       |          | 3.2 x                 |          |      | 43.2 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| float           | sin         | 23.491      |          | 3.550                 | 6.6 x    |      | 0.281                | 83.7 x   |
| array(np.float) | sin         | 6.638       |          | 0.605                 | 11.0 x   |      | 0.015                | 451.7 x  |
| vec speedup     |             | 3.5 x       |          | 5.9 x                 |          |      | 19.1 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| float           | cos         | 20.729      |          | 3.539                 | 5.9 x    |      | 0.299                | 69.3 x   |
| array(np.float) | cos         | 6.625       |          | 0.603                 | 11.0 x   |      | 0.014                | 467.0 x  |
| vec speedup     |             | 3.1 x       |          | 5.9 x                 |          |      | 21.1 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| float           | tan         | 21.281      |          | 3.682                 | 5.8 x    |      | 0.287                | 74.0 x   |
| array(np.float) | tan         | 7.151       |          | 0.768                 | 9.3 x    |      | 0.025                | 290.2 x  |
| vec speedup     |             | 3.0 x       |          | 4.8 x                 |          |      | 11.7 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| float           | log         | 23.290      |          | 3.514                 | 6.6 x    |      | 0.331                | 70.3 x   |
| array(np.float) | log         | 8.475       |          | 0.625                 | 13.6 x   |      | 0.012                | 724.0 x  |
| vec speedup     |             | 2.7 x       |          | 5.6 x                 |          |      | 28.3 x               |          |
|                 |             |             |          |                       |          |      |                      |          |
| for(int)        | matmul      | 9.812       |          | 2.049                 | 4.8 x    |      | 0.274                | 35.9 x   |
| M(np.int16)     | matmul      | 1.146       |          | 0.045                 | 25.5 x   |      | 0.001                | 1200.4 x |
| vec speedup     |             | 8.6 x       |          | 45.6 x                |          |      | 286.5 x              |          |
|                 |             |             |          |                       |          |      |                      |          |
| for(float)      | matmul      | 11.020      |          | 2.632                 | 4.2 x    |      | 0.253                | 43.6 x   |
| M(np.float)     | matmul      | 0.802       |          | 0.041                 | 19.6 x   |      | 0.000                | 1914.1 x |
| vec speedup     |             | 13.7 x      |          | 64.2 x                |          |      | 603.6 x              |          |

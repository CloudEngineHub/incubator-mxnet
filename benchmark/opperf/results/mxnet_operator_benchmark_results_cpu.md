<!--- Licensed to the Apache Software Foundation (ASF) under one -->
<!--- or more contributor license agreements.  See the NOTICE file -->
<!--- distributed with this work for additional information -->
<!--- regarding copyright ownership.  The ASF licenses this file -->
<!--- to you under the Apache License, Version 2.0 (the -->
<!--- "License"); you may not use this file except in compliance -->
<!--- with the License.  You may obtain a copy of the License at -->

<!---   http://www.apache.org/licenses/LICENSE-2.0 -->

<!--- Unless required by applicable law or agreed to in writing, -->
<!--- software distributed under the License is distributed on an -->
<!--- "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY -->
<!--- KIND, either express or implied.  See the License for the -->
<!--- specific language governing permissions and limitations -->
<!--- under the License. -->

# MXNet Operator Benchmarks

## Settings

1. MXNet - v1.4.1
2. Instance - C5.8x

| Operator | Avg Forward Time (ms) | Avg. Backward Time (ms) | Max Mem Usage (Storage) (Bytes) | Inputs |
| :---: | :---: | :---: | :---:| :--- |
| shuffle | 0.8901 | --- | 4194.3042 | {'data': (1024, 1024)} |
| shuffle | 1.2146 | --- | 40.0 | {'data': (10000, 1)} |
| shuffle | 1.8777 | --- | 4000.0 | {'data': (10000, 100)} |
| broadcast_equal | 0.006 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| broadcast_hypot | 0.0108 | 0.0135 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| ceil | 3.4305 | --- | 4194.3042 | {'data': (1024, 1024)} |
| ceil | 0.0507 | --- | 40.0 | {'data': (10000, 1)} |
| ceil | 3.317 | --- | 4000.0 | {'data': (10000, 100)} |
| sum | 32.4206 | 25.5443 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| sum | 0.3393 | 0.2507 | 0.004 | {'data': (10000, 1), 'axis': 0} |
| sum | 31.0189 | 24.7422 | 0.002 | {'data': (10000, 100), 'axis': (0, 1)} |
| broadcast_logical_xor | 0.0068 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| erf | 35.0669 | 16.5842 | 4194.3042 | {'data': (1024, 1024)} |
| erf | 0.3982 | 0.1734 | 40.0 | {'data': (10000, 1)} |
| erf | 29.4103 | 14.3537 | 4000.0 | {'data': (10000, 100)} |
| tanh | 11.2211 | 6.1798 | 2097.1521 | {'data': (1024, 1024)} |
| tanh | 0.1628 | 0.0622 | 40.0 | {'data': (10000, 1)} |
| tanh | 10.7941 | 6.0085 | 4000.0 | {'data': (10000, 100)} |
| arcsinh | 10.0168 | 8.5245 | 2097.1521 | {'data': (1024, 1024)} |
| arcsinh | 0.1111 | 0.0905 | 40.0 | {'data': (10000, 1)} |
| arcsinh | 9.4415 | 7.9082 | 2000.0 | {'data': (10000, 100)} |
| fix | 15.541 | --- | 4194.3042 | {'data': (1024, 1024)} |
| fix | 0.1615 | --- | 40.0 | {'data': (10000, 1)} |
| fix | 14.591 | --- | 4000.0 | {'data': (10000, 100)} |
| broadcast_maximum | 0.0097 | 0.0099 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| sin | 14.4123 | 16.5642 | 2097.1521 | {'data': (1024, 1024)} |
| sin | 0.1459 | 0.156 | 40.0 | {'data': (10000, 1)} |
| sin | 13.821 | 15.4752 | 2000.0 | {'data': (10000, 100)} |
| random_normal | 151.0089 | --- | 4194.3042 | {'shape': (1024, 1024)} |
| random_normal | 1.456 | --- | 40.0 | {'shape': (10000, 1)} |
| random_normal | 144.775 | --- | 2000.0 | {'shape': (10000, 100)} |
| sqrt | 3.3861 | 5.1123 | 2097.1521 | {'data': (1024, 1024)} |
| sqrt | 0.0393 | 0.0548 | 20.0 | {'data': (10000, 1)} |
| sqrt | 3.3037 | 4.7883 | 2000.0 | {'data': (10000, 100)} |
| BlockGrad | 0.3275 | --- | 4194.3042 | {'data': (1024, 1024)} |
| BlockGrad | 0.0161 | --- | 40.0 | {'data': (10000, 1)} |
| BlockGrad | 0.3118 | --- | 4000.0 | {'data': (10000, 100)} |
| sample_exponential | 123.8534 | --- | 8388.6084 | {'lam': [1.0, 8.5], 'shape': (1024, 1024)} |
| sample_exponential | 1.3394 | --- | 80.0 | {'lam': [1.0, 8.5], 'shape': (10000, 1)} |
| sample_exponential | 118.4786 | --- | 8000.0 | {'lam': [1.0, 8.5], 'shape': (10000, 100)} |
| sample_gamma | 529.0305 | --- | 8388.6084 | {'alpha': [0.0, 2.5], 'shape': (1024, 1024), 'beta': [1.0, 0.7]} |
| sample_gamma | 5.7426 | --- | 80.0 | {'alpha': [0.0, 2.5], 'shape': (10000, 1), 'beta': [1.0, 0.7]} |
| sample_gamma | 496.0531 | --- | 8000.0 | {'alpha': [0.0, 2.5], 'shape': (10000, 100), 'beta': [1.0, 0.7]} |
| log2 | 12.3183 | 4.5842 | 2097.1521 | {'data': (1024, 1024)} |
| log2 | 0.1269 | 0.0459 | 40.0 | {'data': (10000, 1)} |
| log2 | 11.6719 | 4.2632 | 4000.0 | {'data': (10000, 100)} |
| broadcast_greater_equal | 0.0092 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| FullyConnected | 18.4677 | 21.6917 | 8.192 | {'data': (32, 3, 256, 256), 'num_hidden': 64, 'weight': (64, 196608), 'bias': (64,), 'flatten': True} |
| FullyConnected | 20.3379 | 38.8295 | 6291.4561 | {'data': (32, 3, 256, 256), 'num_hidden': 64, 'weight': (64, 256), 'bias': (64,), 'flatten': False} |
| cos | 14.8699 | 16.8678 | 2097.1521 | {'data': (1024, 1024)} |
| cos | 0.1511 | 0.1585 | 40.0 | {'data': (10000, 1)} |
| cos | 14.0109 | 15.5246 | 2000.0 | {'data': (10000, 100)} |
| broadcast_mul | 0.0075 | 0.0075 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| arccos | 21.5631 | 12.8768 | 4194.3042 | {'data': (1024, 1024)} |
| arccos | 0.1719 | 0.1084 | 40.0 | {'data': (10000, 1)} |
| arccos | 15.3153 | 7.9161 | 2000.0 | {'data': (10000, 100)} |
| stop_gradient | --- | --- | 4194.3042 | {'data': (1024, 1024)} |
| stop_gradient | --- | --- | 40.0 | {'data': (10000, 1)} |
| stop_gradient | --- | --- | 4000.0 | {'data': (10000, 100)} |
| broadcast_sub | 0.0078 | 0.0059 | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| random_poisson | 112.7425 | --- | 4194.3042 | {'shape': (1024, 1024)} |
| random_poisson | 1.0701 | --- | 40.0 | {'shape': (10000, 1)} |
| random_poisson | 114.3405 | --- | 2000.0 | {'shape': (10000, 100)} |
| rsqrt | 4.3564 | 7.0663 | 2097.1521 | {'data': (1024, 1024)} |
| rsqrt | 0.075 | 0.0861 | 40.0 | {'data': (10000, 1)} |
| rsqrt | 4.5076 | 6.6598 | 4000.0 | {'data': (10000, 100)} |
| nansum | 34.2019 | 57.1624 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| nansum | 0.3683 | 0.5326 | 0.002 | {'data': (10000, 1), 'axis': 0} |
| nansum | 32.9698 | 55.4243 | 0.002 | {'data': (10000, 100), 'axis': (0, 1)} |
| hard_sigmoid | 7.5926 | 6.5839 | 2097.1521 | {'data': (1024, 1024), 'alpha': 0.25, 'beta': 0.5} |
| hard_sigmoid | 0.1086 | 0.0895 | 40.0 | {'data': (10000, 1), 'alpha': 0.25, 'beta': 0.5} |
| hard_sigmoid | 8.1285 | 6.6014 | 4000.0 | {'data': (10000, 100), 'alpha': 0.25, 'beta': 0.5} |
| softmax | 25.4074 | 9.4933 | 2097.1521 | {'data': (1024, 1024), 'axis': -1, 'temperature': 0.5} |
| softmax | 0.4022 | 0.3145 | 40.0 | {'data': (10000, 1), 'axis': -1, 'temperature': 0.5} |
| softmax | 25.604 | 9.4286 | 4000.0 | {'data': (10000, 100), 'axis': -1, 'temperature': 0.5} |
| random_negative_binomial | 285.8721 | --- | 4194.3042 | {'k': 1, 'p': 1, 'shape': (1024, 1024)} |
| random_negative_binomial | 2.839 | --- | 40.0 | {'k': 1, 'p': 1, 'shape': (10000, 1)} |
| random_negative_binomial | 273.034 | --- | 2000.0 | {'k': 1, 'p': 1, 'shape': (10000, 100)} |
| BatchNorm | 66.062 | 88.4693 | 25165.8359 | {'data': (32, 3, 256, 256), 'gamma': (3,), 'beta': (3,), 'moving_mean': (3,), 'moving_var': (3,)} |
| BatchNorm | 101.3006 | 134.4362 | 38400.0117 | {'data': (32, 3, 10000, 10), 'gamma': (3,), 'beta': (3,), 'moving_mean': (3,), 'moving_var': (3,)} |
| Pooling | 0.5533 | 0.6485 | 49.152 | {'data': (32, 3, 256), 'kernel': 3, 'pool_type': 'avg', 'global_pool': 0, 'stride': 1, 'pad': 1, 'layout': 'NCW'} |
| radians | 3.3238 | 3.9704 | 4194.3042 | {'data': (1024, 1024)} |
| radians | 0.0391 | 0.0436 | 40.0 | {'data': (10000, 1)} |
| radians | 3.2462 | 3.775 | 4000.0 | {'data': (10000, 100)} |
| arctanh | 13.3211 | 6.3172 | 2097.1521 | {'data': (1024, 1024)} |
| arctanh | 0.1498 | 0.0683 | 40.0 | {'data': (10000, 1)} |
| arctanh | 12.5376 | 6.0177 | 2000.0 | {'data': (10000, 100)} |
| nanprod | 34.3464 | 57.9841 | 0.004 | {'data': (1024, 1024), 'axis': ()} |
| nanprod | 0.3638 | 0.5336 | 0.004 | {'data': (10000, 1), 'axis': 0} |
| nanprod | 32.83 | 55.2982 | 0.002 | {'data': (10000, 100), 'axis': (0, 1)} |
| elemwise_add | 0.0065 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| cosh | 8.4872 | 10.6597 | 2097.1521 | {'data': (1024, 1024)} |
| cosh | 0.1015 | 0.1201 | 40.0 | {'data': (10000, 1)} |
| cosh | 8.3937 | 10.6244 | 4000.0 | {'data': (10000, 100)} |
| tan | 15.4508 | 6.0752 | 2097.1521 | {'data': (1024, 1024)} |
| tan | 0.1549 | 0.0591 | 40.0 | {'data': (10000, 1)} |
| tan | 14.6992 | 5.802 | 2000.0 | {'data': (10000, 100)} |
| broadcast_not_equal | 0.0054 | --- | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| trunc | 3.493 | --- | 2097.1521 | {'data': (1024, 1024)} |
| trunc | 0.0505 | --- | 40.0 | {'data': (10000, 1)} |
| trunc | 3.1751 | --- | 2000.0 | {'data': (10000, 100)} |
| min_axis | 36.7382 | --- | 0.004 | {'data': (1024, 1024), 'axis': ()} |
| min_axis | 0.4225 | --- | 0.004 | {'data': (10000, 1), 'axis': 0} |
| min_axis | 31.3261 | --- | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| random_uniform | 44.7633 | --- | 4194.3042 | {'low': 0, 'high': 5, 'shape': (1024, 1024)} |
| random_uniform | 0.4607 | --- | 40.0 | {'low': 0, 'high': 5, 'shape': (10000, 1)} |
| random_uniform | 42.9135 | --- | 4000.0 | {'low': 0, 'high': 5, 'shape': (10000, 100)} |
| abs | 4.3965 | 13.406 | 4194.3042 | {'data': (1024, 1024)} |
| abs | 0.0696 | 0.1374 | 40.0 | {'data': (10000, 1)} |
| abs | 4.3552 | 13.7197 | 4000.0 | {'data': (10000, 100)} |
| broadcast_lesser_equal | 0.0054 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| random_randint | 65.414 | --- | 4194.3042 | {'low': 0, 'high': 5, 'shape': (1024, 1024)} |
| random_randint | 0.6331 | --- | 40.0 | {'low': 0, 'high': 5, 'shape': (10000, 1)} |
| random_randint | 61.32 | --- | 4000.0 | {'low': 0, 'high': 5, 'shape': (10000, 100)} |
| log1p | 13.6758 | 5.2497 | 2097.1521 | {'data': (1024, 1024)} |
| log1p | 0.1493 | 0.0562 | 40.0 | {'data': (10000, 1)} |
| log1p | 12.9494 | 5.0609 | 2000.0 | {'data': (10000, 100)} |
| log | 11.9666 | 5.1096 | 4194.3042 | {'data': (1024, 1024)} |
| log | 0.1306 | 0.0588 | 40.0 | {'data': (10000, 1)} |
| log | 11.8985 | 5.0319 | 2000.0 | {'data': (10000, 100)} |
| round | 14.6427 | --- | 4194.3042 | {'data': (1024, 1024)} |
| round | 0.1424 | --- | 20.0 | {'data': (10000, 1)} |
| round | 13.58 | --- | 2000.0 | {'data': (10000, 100)} |
| sample_negative_binomial | 1263.9417 | --- | 8388.6084 | {'k': [20, 49], 'shape': (1024, 1024), 'p': [0.4, 0.77]} |
| sample_negative_binomial | 12.5213 | --- | 80.0 | {'k': [20, 49], 'shape': (10000, 1), 'p': [0.4, 0.77]} |
| sample_negative_binomial | 1207.5739 | --- | 8000.0 | {'k': [20, 49], 'shape': (10000, 100), 'p': [0.4, 0.77]} |
| max | 30.7008 | 55.863 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| max | 0.3287 | 0.5147 | 0.004 | {'data': (10000, 1), 'axis': 0} |
| max | 29.4913 | 53.255 | 0.002 | {'data': (10000, 100), 'axis': (0, 1)} |
| mean | 31.9337 | 35.9235 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| mean | 0.4088 | 0.3453 | 0.002 | {'data': (10000, 1), 'axis': 0} |
| mean | 31.5658 | 34.609 | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| sign | 10.1736 | 4.1682 | 4194.3042 | {'data': (1024, 1024)} |
| sign | 0.1251 | 0.0588 | 40.0 | {'data': (10000, 1)} |
| sign | 9.5196 | 3.9109 | 2000.0 | {'data': (10000, 100)} |
| broadcast_power | 0.0117 | 0.0112 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| argmax_channel | 10.9332 | --- | 4.096 | {'data': (1024, 1024)} |
| argmax_channel | 0.2703 | --- | 40.0 | {'data': (10000, 1)} |
| argmax_channel | 10.7759 | --- | 40.0 | {'data': (10000, 100)} |
| flatten | --- | --- | 4194.3042 | {'data': (1024, 1024)} |
| flatten | --- | --- | 40.0 | {'data': (10000, 1)} |
| flatten | --- | --- | 4000.0 | {'data': (10000, 100)} |
| ones_like | 2.127 | --- | 4194.3042 | {'data': (1024, 1024)} |
| ones_like | 0.028 | --- | 40.0 | {'data': (10000, 1)} |
| ones_like | 1.8846 | --- | 4000.0 | {'data': (10000, 100)} |
| negative | 2.6672 | --- | 4194.3042 | {'data': (1024, 1024)} |
| negative | 0.0321 | --- | 40.0 | {'data': (10000, 1)} |
| negative | 2.4958 | --- | 4000.0 | {'data': (10000, 100)} |
| elemwise_mul | 0.0054 | --- | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| batch_dot | 766.5307 | 1365.6267 | 134217.7344 | {'lhs': (32, 1024, 1024), 'rhs': (32, 1024, 1024)} |
| batch_dot | 37.618 | 46.1098 | 128000.0 | {'lhs': (32, 1000, 10), 'rhs': (32, 1000, 10), 'transpose_b': True} |
| batch_dot | 1.3618 | 4.0882 | 6.4 | {'lhs': (32, 1000, 1), 'rhs': (32, 100, 1000), 'transpose_a': True, 'transpose_b': True} |
| sum_axis | 33.2033 | --- | 0.004 | {'data': (1024, 1024), 'axis': ()} |
| sum_axis | 0.3155 | --- | 0.004 | {'data': (10000, 1), 'axis': 0} |
| sum_axis | 30.9792 | --- | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| floor | 3.5835 | --- | 4194.3042 | {'data': (1024, 1024)} |
| floor | 0.0499 | --- | 20.0 | {'data': (10000, 1)} |
| floor | 3.3519 | --- | 4000.0 | {'data': (10000, 100)} |
| logical_not | 3.0748 | --- | 4194.3042 | {'data': (1024, 1024)} |
| logical_not | 0.0319 | --- | 40.0 | {'data': (10000, 1)} |
| logical_not | 3.0173 | --- | 4000.0 | {'data': (10000, 100)} |
| log10 | 12.3647 | 4.5036 | 2097.1521 | {'data': (1024, 1024)} |
| log10 | 0.1647 | 0.0619 | 40.0 | {'data': (10000, 1)} |
| log10 | 11.7758 | 4.231 | 2000.0 | {'data': (10000, 100)} |
| rcbrt | 11.737 | 14.931 | 2097.1521 | {'data': (1024, 1024)} |
| rcbrt | 0.1241 | 0.1421 | 40.0 | {'data': (10000, 1)} |
| rcbrt | 11.2254 | 14.2139 | 2000.0 | {'data': (10000, 100)} |
| broadcast_logical_or | 0.0093 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| sample_normal | 304.5372 | --- | 8388.6084 | {'mu': [2.0, 2.5], 'shape': (1024, 1024), 'sigma': [1.0, 3.7]} |
| sample_normal | 2.8403 | --- | 80.0 | {'mu': [2.0, 2.5], 'shape': (10000, 1), 'sigma': [1.0, 3.7]} |
| sample_normal | 284.6853 | --- | 8000.0 | {'mu': [2.0, 2.5], 'shape': (10000, 100), 'sigma': [1.0, 3.7]} |
| broadcast_minimum | 0.0073 | 0.0073 | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| arctan | 10.4997 | 6.4532 | 2097.1521 | {'data': (1024, 1024)} |
| arctan | 0.1269 | 0.0683 | 40.0 | {'data': (10000, 1)} |
| arctan | 10.1779 | 6.1741 | 2000.0 | {'data': (10000, 100)} |
| broadcast_mod | 0.0131 | 0.0127 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| size_array | 0.0056 | --- | 0.008 | {'data': (1024, 1024)} |
| size_array | 0.005 | --- | 0.008 | {'data': (10000, 1)} |
| size_array | 0.0081 | --- | 0.004 | {'data': (10000, 100)} |
| make_loss | 0.4874 | --- | 4194.3042 | {'data': (1024, 1024)} |
| make_loss | 0.013 | --- | 40.0 | {'data': (10000, 1)} |
| make_loss | 0.3483 | --- | 4000.0 | {'data': (10000, 100)} |
| broadcast_greater | 0.0082 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| gammaln | 49.6217 | 105.7931 | 2097.1521 | {'data': (1024, 1024)} |
| gammaln | 0.4789 | 0.9577 | 40.0 | {'data': (10000, 1)} |
| gammaln | 48.474 | 102.211 | 4000.0 | {'data': (10000, 100)} |
| broadcast_lesser | 0.0084 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| max_axis | 30.1487 | --- | 0.004 | {'data': (1024, 1024), 'axis': ()} |
| max_axis | 0.3101 | --- | 0.004 | {'data': (10000, 1), 'axis': 0} |
| max_axis | 29.4315 | --- | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| degrees | 3.659 | 4.2964 | 2097.1521 | {'data': (1024, 1024)} |
| degrees | 0.0595 | 0.0538 | 20.0 | {'data': (10000, 1)} |
| degrees | 3.8676 | 4.1255 | 4000.0 | {'data': (10000, 100)} |
| sinh | 8.9259 | 10.3014 | 2097.1521 | {'data': (1024, 1024)} |
| sinh | 0.0989 | 0.1048 | 40.0 | {'data': (10000, 1)} |
| sinh | 8.4579 | 9.7402 | 2000.0 | {'data': (10000, 100)} |
| zeros_like | 2.4764 | --- | 4194.3042 | {'data': (1024, 1024)} |
| zeros_like | 0.0056 | --- | 40.0 | {'data': (10000, 1)} |
| zeros_like | 2.3254 | --- | 4000.0 | {'data': (10000, 100)} |
| arccosh | 6.8035 | 7.7818 | 2097.1521 | {'data': (1024, 1024)} |
| arccosh | 0.0764 | 0.0847 | 40.0 | {'data': (10000, 1)} |
| arccosh | 6.444 | 7.5842 | 2000.0 | {'data': (10000, 100)} |
| prod | 28.2885 | 55.9765 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| prod | 0.2996 | 0.5213 | 0.004 | {'data': (10000, 1), 'axis': 0} |
| prod | 26.9891 | 54.6354 | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| random_gamma | 247.5786 | --- | 2097.1521 | {'shape': (1024, 1024)} |
| random_gamma | 2.3986 | --- | 40.0 | {'shape': (10000, 1)} |
| random_gamma | 237.5963 | --- | 2000.0 | {'shape': (10000, 100)} |
| broadcast_minus | --- | --- | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| Flatten | 0.3339 | --- | 4194.3042 | {'data': (1024, 1024)} |
| Flatten | 0.0152 | --- | 40.0 | {'data': (10000, 1)} |
| Flatten | 0.3546 | --- | 4000.0 | {'data': (10000, 100)} |
| expm1 | 9.8241 | 11.7609 | 4194.3042 | {'data': (1024, 1024)} |
| expm1 | 0.1844 | 0.1675 | 40.0 | {'data': (10000, 1)} |
| expm1 | 9.0366 | 10.4387 | 4000.0 | {'data': (10000, 100)} |
| elemwise_div | 0.0064 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| LeakyReLU | 10.3625 | 12.5441 | 4194.3042 | {'data': (1024, 1024), 'act_type': 'leaky', 'slope': 0.1} |
| LeakyReLU | 0.1076 | 0.1277 | 40.0 | {'data': (10000, 1), 'act_type': 'leaky', 'slope': 0.1} |
| LeakyReLU | 9.5913 | 11.7957 | 2000.0 | {'data': (10000, 100), 'act_type': 'leaky', 'slope': 0.1} |
| LeakyReLU | 12.337 | 12.6383 | 2097.1521 | {'data': (1024, 1024), 'act_type': 'elu', 'slope': 0.1} |
| LeakyReLU | 0.1305 | 0.1217 | 40.0 | {'data': (10000, 1), 'act_type': 'elu', 'slope': 0.1} |
| LeakyReLU | 11.652 | 11.8465 | 4000.0 | {'data': (10000, 100), 'act_type': 'elu', 'slope': 0.1} |
| LeakyReLU | 12.4973 | 11.4957 | 2097.1521 | {'data': (1024, 1024), 'act_type': 'selu'} |
| LeakyReLU | 0.1295 | 0.1176 | 40.0 | {'data': (10000, 1), 'act_type': 'selu'} |
| LeakyReLU | 12.2224 | 11.548 | 4000.0 | {'data': (10000, 100), 'act_type': 'selu'} |
| LeakyReLU | 16.9543 | 306.6579 | 2097.1521 | {'data': (1024, 1024), 'act_type': 'prelu', 'gamma': (1, 1024)} |
| LeakyReLU | 0.2859 | 1.9528 | 20.0 | {'data': (10000, 1), 'act_type': 'prelu', 'gamma': (1, 1)} |
| LeakyReLU | 16.0125 | 231.8273 | 2000.0 | {'data': (10000, 100), 'act_type': 'prelu', 'gamma': (1, 100)} |
| rint | 14.9397 | --- | 4194.3042 | {'data': (1024, 1024)} |
| rint | 0.1535 | --- | 40.0 | {'data': (10000, 1)} |
| rint | 14.5915 | --- | 4000.0 | {'data': (10000, 100)} |
| identity | --- | --- | 4194.3042 | {'data': (1024, 1024)} |
| identity | --- | --- | 40.0 | {'data': (10000, 1)} |
| identity | --- | --- | 4000.0 | {'data': (10000, 100)} |
| softsign | 3.9985 | 7.05 | 2097.1521 | {'data': (1024, 1024)} |
| softsign | 0.0486 | 0.0737 | 40.0 | {'data': (10000, 1)} |
| softsign | 3.7662 | 6.7975 | 2000.0 | {'data': (10000, 100)} |
| broadcast_div | 0.0083 | 0.0075 | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| square | 4.2037 | 4.9639 | 2097.1521 | {'data': (1024, 1024)} |
| square | 0.0467 | 0.0558 | 40.0 | {'data': (10000, 1)} |
| square | 3.9986 | 4.6533 | 2000.0 | {'data': (10000, 100)} |
| elemwise_sub | 0.0058 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| dot | 14.562 | 29.1605 | 4194.3042 | {'lhs': (1024, 1024), 'rhs': (1024, 1024)} |
| dot | 0.745 | 1.5842 | 2000.0 | {'lhs': (1000, 10), 'rhs': (1000, 10), 'transpose_b': True} |
| dot | 0.0579 | 0.1673 | 0.2 | {'lhs': (1000, 1), 'rhs': (100, 1000), 'transpose_a': True, 'transpose_b': True} |
| broadcast_logical_and | 0.0071 | --- | 0.024 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| broadcast_add | 0.0081 | 0.0066 | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| random_exponential | 63.2732 | --- | 4194.3042 | {'shape': (1024, 1024)} |
| random_exponential | 0.6453 | --- | 40.0 | {'shape': (10000, 1)} |
| random_exponential | 59.2788 | --- | 2000.0 | {'shape': (10000, 100)} |
| Dropout | 249.4661 | 23.5141 | 37748.7344 | {'data': (32, 3, 256, 256), 'p': 0.5, 'mode': 'always'} |
| Dropout | 3.9634 | 0.3516 | 600.0 | {'data': (10000, 10), 'p': 0.5, 'mode': 'always'} |
| exp | 8.9413 | --- | 4194.3042 | {'data': (1024, 1024)} |
| exp | 0.0971 | --- | 40.0 | {'data': (10000, 1)} |
| exp | 7.9211 | --- | 4000.0 | {'data': (10000, 100)} |
| random_generalized_negative_binomial | 362.7789 | --- | 2097.1521 | {'shape': (1024, 1024)} |
| random_generalized_negative_binomial | 3.4276 | --- | 40.0 | {'shape': (10000, 1)} |
| random_generalized_negative_binomial | 344.3516 | --- | 4000.0 | {'shape': (10000, 100)} |
| min | 30.8723 | 55.9413 | 0.002 | {'data': (1024, 1024), 'axis': ()} |
| min | 0.3168 | 0.5206 | 0.002 | {'data': (10000, 1), 'axis': 0} |
| min | 29.9547 | 53.8245 | 0.004 | {'data': (10000, 100), 'axis': (0, 1)} |
| erfinv | 79.987 | 99.2274 | 2097.1521 | {'data': (1024, 1024)} |
| erfinv | 0.7567 | 0.9105 | 40.0 | {'data': (10000, 1)} |
| erfinv | 76.0479 | 95.5001 | 2000.0 | {'data': (10000, 100)} |
| broadcast_plus | --- | --- | 0.012 | {'lhs': [(1024, 1024), (10000, 10), (10000, 1)], 'rhs': [(1024, 1024), (10000, 10), (10000, 1)]} |
| arcsin | 16.3157 | 7.6156 | 2097.1521 | {'data': (1024, 1024)} |
| arcsin | 0.1611 | 0.0758 | 40.0 | {'data': (10000, 1)} |
| arcsin | 16.0225 | 7.5081 | 2000.0 | {'data': (10000, 100)} |
| sample_generalized_negative_binomial | 629.1785 | --- | 8388.6084 | {'mu': [2.0, 2.5], 'shape': (1024, 1024), 'alpha': [0.0, 2.5]} |
| sample_generalized_negative_binomial | 6.8681 | --- | 80.0 | {'mu': [2.0, 2.5], 'shape': (10000, 1), 'alpha': [0.0, 2.5]} |
| sample_generalized_negative_binomial | 604.3484 | --- | 8000.0 | {'mu': [2.0, 2.5], 'shape': (10000, 100), 'alpha': [0.0, 2.5]} |
| relu | 11.0979 | 8.3262 | 2097.1521 | {'data': (1024, 1024)} |
| relu | 0.1163 | 0.0853 | 40.0 | {'data': (10000, 1)} |
| relu | 10.6863 | 8.0702 | 4000.0 | {'data': (10000, 100)} |
| cbrt | 11.3121 | 6.5254 | 2097.1521 | {'data': (1024, 1024)} |
| cbrt | 0.1238 | 0.0687 | 40.0 | {'data': (10000, 1)} |
| cbrt | 10.4631 | 6.0997 | 2000.0 | {'data': (10000, 100)} |
| sample_uniform | 89.1332 | --- | 8388.6084 | {'low': [0.0, 2.5], 'shape': (1024, 1024), 'high': [1.0, 3.7]} |
| sample_uniform | 0.8895 | --- | 80.0 | {'low': [0.0, 2.5], 'shape': (10000, 1), 'high': [1.0, 3.7]} |
| sample_uniform | 84.4477 | --- | 8000.0 | {'low': [0.0, 2.5], 'shape': (10000, 100), 'high': [1.0, 3.7]} |
| Convolution | 13.4072 | 17.0238 | 56610.418 | {'data': (32, 3, 256), 'weight': (64, 3, 3), 'bias': (64,), 'kernel': (3,), 'stride': (1,), 'dilate': (1,), 'pad': (0,), 'num_filter': 64, 'layout': 'NCW'} |
| sample_poisson | 512.1068 | --- | 8388.6084 | {'lam': [1.0, 8.5], 'shape': (1024, 1024)} |
| sample_poisson | 4.6203 | --- | 80.0 | {'lam': [1.0, 8.5], 'shape': (10000, 1)} |
| sample_poisson | 474.1238 | --- | 8000.0 | {'lam': [1.0, 8.5], 'shape': (10000, 100)} |
| log_softmax | 21.4413 | 15.7456 | 2097.1521 | {'data': (1024, 1024), 'axis': -1, 'temperature': 0.5} |
| log_softmax | 0.4613 | 0.2958 | 20.0 | {'data': (10000, 1), 'axis': -1, 'temperature': 0.5} |
| log_softmax | 21.9745 | 15.2407 | 4000.0 | {'data': (10000, 100), 'axis': -1, 'temperature': 0.5} |
| gamma | 35.1027 | 124.2015 | 2097.1521 | {'data': (1024, 1024)} |
| gamma | 0.3611 | 1.1177 | 20.0 | {'data': (10000, 1)} |
| gamma | 33.636 | 117.6889 | 2000.0 | {'data': (10000, 100)} |
| reciprocal | 3.4646 | 6.1106 | 2097.1521 | {'data': (1024, 1024)} |
| reciprocal | 0.0413 | 0.0635 | 40.0 | {'data': (10000, 1)} |
| reciprocal | 3.2553 | 5.8762 | 2000.0 | {'data': (10000, 100)} |
| sigmoid | 9.8017 | 5.9639 | 2097.1521 | {'data': (1024, 1024)} |
| sigmoid | 0.1095 | 0.0651 | 40.0 | {'data': (10000, 1)} |
| sigmoid | 9.0443 | 5.7901 | 2000.0 | {'data': (10000, 100)} |
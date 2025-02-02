# ProximalAlgorithms.jl

[![Build status](https://github.com/JuliaFirstOrder/ProximalAlgorithms.jl/workflows/CI/badge.svg)](https://github.com/JuliaFirstOrder/ProximalAlgorithms.jl/actions?query=workflow%3ACI)
[![codecov.io](http://codecov.io/github/JuliaFirstOrder/ProximalAlgorithms.jl/coverage.svg?branch=master)](http://codecov.io/github/JuliaFirstOrderProximalAlgorithms.jl?branch=master)

Proximal algorithms (also known as "splitting" algorithms or methods) for nonsmooth optimization in Julia.

This package can be used in combination with [ProximalOperators.jl](https://github.com/JuliaFirstOrder/ProximalOperators.jl) (providing first-order primitives, i.e. gradient and proximal mapping, for numerous cost functions) and [AbstractOperators.jl](https://github.com/kul-forbes/AbstractOperators.jl) (providing several linear and nonlinear operators) to formulate and solve a wide spectrum of nonsmooth optimization problems.

[StructuredOptimization.jl](https://github.com/JuliaFirstOrder/StructuredOptimization.jl) provides a higher-level interface to formulate and solve problems using (some of) the algorithms here included.

### Quick start

To install the package, simply issue the following command in the Julia REPL:

```julia
] add ProximalAlgorithms
```

Check out [these test scripts](test/problems) for examples on how to apply
the provided algorithms to problems.

### Implemented Algorithms

Algorithm                             | Function      | Reference
--------------------------------------|---------------|-----------
Douglas-Rachford splitting algorithm  | [`DouglasRachford`](src/algorithms/douglasrachford.jl) | [[1]][eckstein_1989]
Forward-backward splitting (i.e. proximal gradient) algorithm | [`ForwardBackward`](src/algorithms/forwardbackward.jl) | [[2]][tseng_2008], [[3]][beck_2009]
Vũ-Condat primal-dual algorithm       | [`VuCondat`](src/algorithms/primaldual.jl) | [[4]][chambolle_2011], [[6]][vu_2013], [[7]][condat_2013]
Davis-Yin splitting algorithm         | [`DavisYin`](src/algorithms/davisyin.jl) | [[9]][davis_2017]
Asymmetric forward-backward-adjoint algorithm | [`AFBA`](src/algorithms/primaldual.jl) | [[10]][latafat_2017]
PANOC (L-BFGS)                        | [`PANOC`](src/algorithms/panoc.jl) | [[11]][stella_2017]
ZeroFPR (L-BFGS)                      | [`ZeroFPR`](src/algorithms/zerofpr.jl) | [[12]][themelis_2018]
Douglas-Rachford line-search (L-BFGS) | [`DRLS`](src/algorithms/drls.jl) | [[13]][themelis_2020]

### Contributing

Contributions are welcome in the form of [issues notification](https://github.com/JuliaFirstOrder/ProximalAlgorithms.jl/issues) or [pull requests](https://github.com/JuliaFirstOrder/ProximalAlgorithms.jl/pulls). We recommend looking at already implemented algorithms to get inspiration on how to structure new ones.

### References

[[1]][eckstein_1989] Eckstein, Bertsekas, *On the Douglas-Rachford Splitting Method and the Proximal Point Algorithm for Maximal Monotone Operators*, Mathematical Programming, vol. 55, no. 1, pp. 293-318 (1989).

[[2]][tseng_2008] Tseng, *On Accelerated Proximal Gradient Methods for Convex-Concave Optimization* (2008).

[[3]][beck_2009] Beck, Teboulle, *A Fast Iterative Shrinkage-Thresholding Algorithm for Linear Inverse Problems*, SIAM Journal on Imaging Sciences, vol. 2, no. 1, pp. 183-202 (2009).

[[4]][chambolle_2011] Chambolle, Pock, *A First-Order Primal-Dual Algorithm for Convex Problems with Applications to Imaging*, Journal of Mathematical Imaging and Vision, vol. 40, no. 1, pp. 120-145 (2011).

[[5]][boyd_2011] Boyd, Parikh, Chu, Peleato, Eckstein, *Distributed Optimization and Statistical Learning via the Alternating Direction Method of Multipliers*, Foundations and Trends in Machine Learning, vol. 3, no. 1, pp. 1-122 (2011).

[[6]][vu_2013] Vũ, *A splitting algorithm for dual monotone inclusions involving cocoercive operators*, Advances in Computational Mathematics, vol. 38, no. 3, pp. 667-681 (2013).

[[7]][condat_2013] Condat, *A primal–dual splitting method for convex optimization involving Lipschitzian, proximable and linear composite terms*, Journal of Optimization Theory and Applications, vol. 158, no. 2, pp 460-479 (2013).

[[8]][parikh_2014] Parikh, Boyd, *Proximal Algorithms*, Foundations and Trends in Optimization, vol. 1, no. 3, pp. 127-239 (2014).

[[9]][davis_2017] Davis, Yin, *A Three-Operator Splitting Scheme and its Optimization Applications*, Set-Valued and Variational Analysis, vol. 25, no. 4, pp. 829–858 (2017).

[[10]][latafat_2017] Latafat, Patrinos, *Asymmetric forward–backward–adjoint splitting for solving monotone inclusions involving three operators*, Computational Optimization and Applications, vol. 68, no. 1, pp. 57-93 (2017).

[[11]][stella_2017] Stella, Themelis, Sopasakis, Patrinos, *A simple and efficient algorithm for nonlinear model predictive control*, 56th IEEE Conference on Decision and Control (2017).

[[12]][themelis_2018] Themelis, Stella, Patrinos, *Forward-backward envelope for the sum of two nonconvex functions: Further properties and nonmonotone line-search algorithms*, SIAM Journal on Optimization, vol. 28, no. 3, pp. 2274–2303 (2018).

[[13]][themelis_2020] Themelis, Stella, Patrinos, *Douglas-Rachford splitting and ADMM for nonconvex optimization: Accelerated and Newton-type algorithms*, arXiv preprint (2020).


[eckstein_1989]: https://link.springer.com/article/10.1007/BF01581204
[tseng_2008]: http://www.mit.edu/~dimitrib/PTseng/papers/apgm.pdf
[beck_2009]: http://epubs.siam.org/doi/abs/10.1137/080716542
[chambolle_2011]: https://link.springer.com/article/10.1007/s10851-010-0251-1
[boyd_2011]: http://www.nowpublishers.com/article/Details/MAL-016
[parikh_2014]: http://www.nowpublishers.com/article/Details/OPT-003
[themelis_2018]: https://epubs.siam.org/doi/10.1137/16M1080240
[latafat_2017]: https://link.springer.com/article/10.1007/s10589-017-9909-6
[stella_2017]: https://doi.org/10.1109/CDC.2017.8263933
[condat_2013]: https://link.springer.com/article/10.1007/s10957-012-0245-9
[vu_2013]: https://link.springer.com/article/10.1007/s10444-011-9254-8
[davis_2017]: https://link.springer.com/article/10.1007/s11228-017-0421-z
[themelis_2020]: https://arxiv.org/abs/2005.10230

<html>
  <head>
    <title>A high-performance and energy-efficient exhaustive key search approach via GPU on DES-like cryptosystems – Omid Hajihassani – University of Alberta</title>

        <meta charset="utf-8" />
    <meta content='text/html; charset=utf-8' http-equiv='Content-Type'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0'>
    <meta name="description" content="In thie post, I am going to explain the bitslicing technique used in the implementation of a fast GPU-based DES cryptanalysis system that can be applied to other software based implementations. By changing the representation of the data and computations, the bitslicing technique achieves full vectorized SIMD execution on parallel hardware platforms." />
    <meta property="og:description" content="In thie post, I am going to explain the bitslicing technique used in the implementation of a fast GPU-based DES cryptanalysis system that can be applied to other software based implementations. By changing the representation of the data and computations, the bitslicing technique achieves full vectorized SIMD execution on parallel hardware platforms." />
    
  </head>

  <body>
    <div class="wrapper-masthead">
      <div class="container">
        <header class="masthead clearfix">
        </header>
      </div>
    </div>

    <div id="main" role="main" class="container">
      <article class="post">
  <h1>A high-performance and energy-efficient exhaustive key search approach via GPU on DES-like cryptosystems</h1>
  <div>Authors: Omid Hajihassani, Armin Ahmadzadeh, Saeid Gorgin
  <a href="https://link.springer.com/article/10.1007/s11227-017-2120-9">(Link)</a></div>
  <br />
  <div class="entry">
  <h2>Abstract</h2>
    <p>Recently, graphical processing units (GPUs) have found a prominent role in general-purpose applications. Specifically, in parallel processing applications where a considerable number of tasks should be processed while meeting specific design constraints. One of the most interesting subjects in this area is cipher breaking via brute-force attacks, which attracts the attention of many researchers to the field. In this paper, we introduce a novel exhaustive key search approach for block cipher cryptosystems. The key point is how to utilize the single instruction multiple thread architecture to improve the speed of the DES-like hardware-based cryptosystems. At first, the standard DES core is implemented while all operations like bit permutation, swapping, and general hardware data stream follow the original algorithm. Then, in order to maximize the usage of the memory bandwidth and to eliminate the bit access penalty in GPU architecture, we exploit the register permutation and swapping (instead of the conventional bit swapping) in our implementation. In this approach, each thread examines a set of 32 keys per each iteration and hence a considerable throughput is achieved. The experimental results demonstrate 24K  × , 800  × , and 400  ×  speed up over the traditional DES implementation on single-core CPU, the best previous work on multi-core CPU, and the conventional implementation on GPU, respectively. Furthermore, we measure the power and energy consumption of the best GPU and CPU approaches, where the GPU implementation proves to be more power efficient.</p>

<ul>
  <li>Introduction</li>
</ul>

<p>TEXT</p>

<p>TEXT</p>

<ul>
  <li>Motivations</li>
</ul>

<p>TEXT</p>

<p>TEXT</p>

<p>TEXT</p>

<ul>
  <li>Challenges and Opportunities</li>
</ul>

<p>TEXT</p>

<p>TEXT</p>

<ul>
  <li>References</li>
</ul>

<p>[1]REFe.</p>


  </div>

  <div class="date">
    Written on May 24, 2018
  </div>

  
</article>
</body>
</html>

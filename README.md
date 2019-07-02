<html>
  <head>
    <title>A high-performance and energy-efficient exhaustive key search approach via GPU on DES-like cryptosystems – Omid Hajihassani – University of Alberta</title>

        <meta charset="utf-8" />
    <meta content='text/html; charset=utf-8' http-equiv='Content-Type'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <meta name='viewport' content='width=device-width, initial-scale=1.0, maximum-scale=1.0'>

    
    <meta name="description" content="The rapid rise in the connected sensors, actuators, and their accompanying applications surrounding us, often collectively referred to as the Internet of Things (IoT) has lead to a growing interest and attention from the governments, the industry, the scientific community amongst other communities. The numerous opportunities presented by the IoT industry, however, often come at the cost of excessive energy usage, or privacy and security threats, in exchange for fine-grained sensing and data analytics. In this post, I advocate for the use of optimisation trade-offs between the utility and value gained from information, the privacy risks and security threats to the data subject, and the cost (e.g., energy and bandwidth) of performing the sensing and analytics. We argue for leveraging the network edge (i.e., the IoT device itself) to support this optimisation process and provide a cooperative framework between the edge and the cloud. Such an architecture will play a pivotal role in protecting the individuals’ privacy, while reducing the cost of the operation and the privacy and security risks.

" />
    <meta property="og:description" content="The rapid rise in the connected sensors, actuators, and their accompanying applications surrounding us, often collectively referred to as the Internet of Things (IoT) has lead to a growing interest and attention from the governments, the industry, the scientific community amongst other communities. The numerous opportunities presented by the IoT industry, however, often come at the cost of excessive energy usage, or privacy and security threats, in exchange for fine-grained sensing and data analytics. In this post, I advocate for the use of optimisation trade-offs between the utility and value gained from information, the privacy risks and security threats to the data subject, and the cost (e.g., energy and bandwidth) of performing the sensing and analytics. We argue for leveraging the network edge (i.e., the IoT device itself) to support this optimisation process and provide a cooperative framework between the edge and the cloud. Such an architecture will play a pivotal role in protecting the individuals’ privacy, while reducing the cost of the operation and the privacy and security risks.

" />
    
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
  <h1>Analytics on the Edge (Privacy, Utility, and Cost)</h1>

  <div class="entry">
    <p>The rapid rise in the connected sensors, actuators, and their accompanying applications surrounding us, often collectively referred to as the Internet of Things (IoT) has lead to a growing interest and attention from the governments, the industry, the scientific community amongst other communities. The numerous opportunities presented by the IoT industry, however, often come at the cost of excessive energy usage, or privacy and security threats, in exchange for fine-grained sensing and data analytics. In this post, I advocate for the use of optimisation trade-offs between the utility and value gained from information, the privacy risks and security threats to the data subject, and the cost (e.g., energy and bandwidth) of performing the sensing and analytics. We argue for leveraging the network edge (i.e., the IoT device itself) to support this optimisation process and provide a cooperative framework between the edge and the cloud. Such an architecture will play a pivotal role in protecting the individuals’ privacy, while reducing the cost of the operation and the privacy and security risks.</p>

<ul>
  <li>Introduction</li>
</ul>

<p>There is a rapid introduction of the Internet of Things (IoT) devices in our daily lives, from always-on voice-enabled home assistants such as Amazon Alexa and Google Home, to smart thermostats, plugs, toys, and remote monitoring devices. <a href="https://www.gartner.com/newsroom/id/3598917">Gartner predicts</a> that by 2020, we will have over 20 Billion IoT devices in use and connected to the Internet. Presence of such a large number of devices will introduce new challenges in connectivity, data management, privacy, and security.</p>

<p>In parallel with this trend in IoT, advances in machine learning, particularly unsupervised methods such as Deep Learning, on mobile and edge devices have enabled these devices to act as part of the whole data analytics ecosystem, performing a first set of local inferences (e.g., activity recognition on a smartphone), hence redeeming the network from transmitting costly, raw sensor data to the cloud. These challenges can be broadly categorised as the tension between data quality, the cost of obtaining such data, and the privacy (and arguably security) consequences.</p>

<ul>
  <li>Motivations</li>
</ul>

<p>Personal IoT devices might collect a range of rich, sensitive devices about individuals and households. In addition to the privacy risks of exposing these data to their primary collectors, third parties with access to these data also pose security and privacy threats. These include data from autonomous vehicles, smart meters, home security systems, child monitors, and personal health and well-being devices.</p>

<p>Today’s IoT ecosystem relies on continuous data collection and offloading to cloud services. As the numbers and complexity of these devices grows, this modus operandi can have dire network/energy costs and privacy consequences, especially considering the huge volumes of data generated by some of these systems. On the other hand, relying on performing complex data analytics on the device, or encryption-based methods, impose resource constraints (e.g., storage and bandwidth constraints, energy limitations, or computational costs) and jeopardise the user experience. Cryptography-based approaches for data encryption and analytics are often too costly and complex to implement on IoT devices protecting these data. The promise of edge computing, i.e., relying on complete local analytics can also introduce a burden for devices, as most machine learning models are large and complex.</p>

<table>
  <thead>
    <tr>
      <th style="text-align: center"><img src="https://github.com/haddadi/haddadi.github.io/blob/master/images/2018/HybridEngine.png?raw=true" height="150" width="400" /></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center">Hybrid Analytic Engine</td>
    </tr>
  </tbody>
</table>

<p>Her we advocate for a cooperative, hybrid approach between the edge and the cloud. The high-level overview of this scheme is visualised in Figure above, the raw sensor data goes through an initial layer of feature extraction on the device using lightweight, simple models to perform dimensional reduction and compression, while providing a privacy shield against detailed, invasive analysis using well-known privacy techniques. The more complex and intensive analytics take place at the cloud server. One of the primary objectives of this scheme is to separate the feature extraction and the inference phase between the edge device and the cloud. This approach can potentially lead to a reduction in data transmission to the cloud and removal of potentially sensitive information during the feature extraction phase on the edge node. The extracted features are then transferred to the cloud server for post-processing and finally the user receives the results from the cloud.</p>

<ul>
  <li>Challenges and Opportunities</li>
</ul>

<p>There are a number of future directions which naturally follow on from advances in edge computing for the IoT domains. Techniques such as Federated Learning can directly benefit from the proposed hybrid edge-cloud schemes, where nano-updates can be aggregated in a centralised fashion without the threat of de-identification faced by traditional machine learning models. Further, Privacy-preserving approaches such as Auto-encoders or differential privacy can be employed on edge devices to help protect against privacy threats facing traditional deep-learning and federated learning models.</p>

<p>The approach proposed in this vision might not be the silver bullet in defending against IoT security and privacy attacks, or limiting all the bandwidth requirements of future IoT systems. However, research in this area provides a promising direction in improving the status quo and providing a framework for balancing the trade-offs between risks and threats (privacy-security), utility, and operational costs in a broad setting.</p>

<ul>
  <li>References</li>
</ul>

<p>[1]  N. Apthorpe, D. Reisman, S. Sundaresan, A. Narayanan, and N. Feamster, “Spying on the smart home: Privacy attacks and defenses on encrypted IoT traffic”, CoRR, abs/1708.05044, 2017.</p>

<p>[2]  R. C. Geyer, T. Klein, and M. Nabi. “Differentially private federated learning: A client level perspective”, CoRR, abs/1712.07557, 2017.</p>

<p>[3]  B. Hitaj, G. Ateniese, and F. Perez-Cruz, “Deep models under the GAN: Information leakage from collaborative deep learning”, In Proceedings of the 2017 ACM SIGSAC Conference on Computer and Communications Security, CCS ’17, pages 603–618, New York, NY, USA, 2017. ACM.</p>

<p>[4]  J. Konecny, H. B. McMahan, F. X. Yu,P. Richtarik, A. T. Suresh, and D. Bacon, “Federated learning:  Strategies for improving communication efficiency”, CoRR, abs/1610.05492,2016.</p>

<p>[5]  M. Malekzadeh, R. G. Clegg, A. Cavallaro, and H. Haddadi, “Protecting sensory data against sensitive inferences”, In Proceedings of the 1st Workshop on Privacy by Design in Distributed Systems, W-P2DS’18, pages 2:1–2:6, New York, NY, USA, 2018. ACM.</p>

<p>[6]  S. A. Osia, A. S. Shamsabadi, A. Taheri, H. R.Rabiee, and H. Haddadi, “Private and scalable personal data analytics using a hybrid edge-cloud deep learning”, IEEE Computer, 2018.</p>

<p>[7]  C. Zhang, P. Patras, and H. Haddadi, “Deep learning in mobile and wireless networking:  A survey”, arXiv preprint arXiv:1803.04311, 2018.</p>


  </div>

  <div class="date">
    Written on May 24, 2018
  </div>

  
</article>

    </div>

    <div class="wrapper-footer">
      <div class="container">
        <footer class="footer">
          



<a href="https://github.com/haddadi"><i class="svg-icon github"></i></a>

<a href="https://www.linkedin.com/in/haddadi"><i class="svg-icon linkedin"></i></a>


<a href="https://www.twitter.com/realhamed"><i class="svg-icon twitter"></i></a>



        </footer>
      </div>
    </div>

    

  </body>
</html>

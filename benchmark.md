---
layout: default
title: Benchmark Results
Author: Anyka B
---

<div align="center">
    <h1>Course Catalog Benchmarks</h1>
</div>
<br>

<div align="left">
    <p>Benchmark testing is a standardized evaluation used to measure and compare the performance, quality, or efficiency of a system, application, program, or function. These tests establish a performance baseline by measuring metrics such as execution speed, latency, throughput, and memory usage. Benchmark tests proves whether a code optimization or enhancement actually improved the application speed and discover any performance bugs.</p>
    <p>In my data structure and algorithms enhancement, I upgraded the original vector-based course catalog program to a unordered map. Even though theoretically an unordered map outperforms a vector, theoretical time complexity often fails to predict real-world performance. Iterating or searching through a vector can be incredibly fast because of excellent cache coherence, while unordered maps constantly waits to pull fragmented data from the main RAM. These feature differences make it imperative to prove the data structure upgrade was beneficial to the application.</p>
    <p>Additionally, I recreated the course catalog program in Java, as Java can be preferred for velocity, code maintainability, and built-in safety features. Refactoring an application to another language is considered a heavy architectural change. C++ and Java vastly differ in their memory management, predictability, compilation times, and platform independence. Because the two languages are so different, it cannot be assumed that the performance will remain identical. Benchmarking helps measure, understand, and mitigate structural shifts.</p>
    <p>These benchmark tests will analyze the efficiency of each structural and algorithmic differences to discover which implementation is the most efficient.</p>
    <h2> Repo </h2>
</div>
<div align="left">
    <h2>Benchmark Summary</h2>
    <img src="{{ '/assets/img/File_parse_chart.png' | relative_url }}" alt="File Parse Chart">
    <img src="{{ '/assets/img/Course_sort_chart.png' | relative_url }}" alt="Course Sort Chart">
    <img src="{{ '/assets/img/CompSci_chart_chart.png' | relative_url }}" alt="CompSci Course Sort Chart">
    <img src="{{ '/assets/img/key_value_lookup_chart.png' | relative_url }}" alt="Key-value lookup chart">
    <img src="{{ '/assets/img/1k_execution_chart.png' | relative_url }}" alt="1k execution chart">
    <img src="{{ '/assets/img/5k_execution_chart.png' | relative_url }}" alt="5k execution chart">
    <img src="{{ '/assets/img/10k_execution_chart.png' | relative_url }}" alt="10k execution chart">
    <h2>Conclusion</h2>
    <h2>Benchmark Data</h2>
    <h3>File Parsing Time</h3>
    <p>Metric: Input/Output parsing and object instantiation efficiency</p>
    <p>Description: How efficiently each program performs parsing, string-to-number conversions, memory allocation, and inserting data into data structures.</p>
    <!-- C++ Vector -->
    <table>
        <caption>C++ Vector (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>30,379</td>
          <td>1,411,199</td>
          <td>1,019,805</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>40,320</td>
          <td>2,551,524</td>
          <td>5,743,642</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>16,912</td>
          <td>976,959</td>
          <td>1,083,447</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>10,134</td>
          <td>366,165</td>
          <td>921,459</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>24,436</td>
          <td>1,326,462</td>
          <td>2,192,088.25</td>
        </tr>
        <!-- Average Time (s) -->
        <tr>
          <td>Average Time (s)</td>
          <td>0.024</td>
          <td>1.326</td>
          <td>2.192</td>
        </tr>
    </table>
    <!-- C++ unordered_map -->
    <table>
        <caption>C++ unordered_map (2.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>15,584</td>
          <td>212,017</td>
          <td>661,219</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>15,813</td>
          <td>217,283</td>
          <td>653,536</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>17,085</td>
          <td>212,038</td>
          <td>641,956</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>16,302</td>
          <td>204,575</td>
          <td>641,709</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>16,196</td>
          <td>211,478</td>
          <td>649,605</td>
        </tr>
        <!-- Average Time (s) -->
        <tr>
          <td>Average Time (s)</td>
          <td>0.016</td>
          <td>0.211</td>
          <td>0.649</td>
        </tr>
    </table>
    <!-- Java HashMap -->
    <table>
        <caption>Java HashMap (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>318,984</td>
          <td>1,276,079</td>
          <td>2,270,027</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>360,765</td>
          <td>1,155,739</td>
          <td>2,252,839</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>285,561</td>
          <td>1,128,182</td>
          <td>2,132,889</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>296,310</td>
          <td>1,201,960</td>
          <td>2,084,833</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>315,405</td>
          <td>1,190,490</td>
          <td>2,185,147</td>
        </tr>
        <!-- Average Time (s) -->
        <tr>
          <td>Average Time (s)</td>
          <td>0.315</td>
          <td>1.19</td>
          <td>2.185</td>
        </tr>
    </table>
<hr>
    <h3>Sorting Time (printCatalog)</h3>
    <p>Metric: Algorithmic time complexity (sdt::sort vs. Collections.sort)</p>
    <p>Description: The speed of the alphanumeric sorting algorithms when ordering keys. It tests contiguous data structures against key extractions.</p>
    <!-- C++ unordered_map -->
    <table>
        <caption>C++ unordered_map (2.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>62</td>
          <td>75</td>
          <td>148</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>27</td>
          <td>75</td>
          <td>146</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>26</td>
          <td>126</td>
          <td>147</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>48</td>
          <td>89</td>
          <td>147</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>40.75</td>
          <td>91.25</td>
          <td>147</td>
        </tr>
    </table>
    <!-- Java HashMap -->
    <table>
        <caption>Java HashMap (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>118</td>
          <td>679</td>
          <td>734</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>81</td>
          <td>705</td>
          <td>420</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>89</td>
          <td>261</td>
          <td>346</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>130</td>
          <td>125</td>
          <td>274</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>104.5</td>
          <td>442.5</td>
          <td>443.5</td>
        </tr>
    </table>
    <hr>
    <h3>Sorting Time (printCompSciCatalog)</h3>
    <p>Metric: Algorithmic time complexity (sdt::sort vs. Collections.sort)</p>
    <p>Description: The speed of the alphanumeric sorting algorithms when ordering keys. It tests contiguous data structures against key extractions.</p>
    <!-- C++ Vector -->
    <table>
        <caption>C++ Vector (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>20</td>
          <td>1,401</td>
          <td>19,729</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>19</td>
          <td>1,668</td>
          <td>22,518</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>22</td>
          <td>1,840</td>
          <td>30,326</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>20</td>
          <td>1,339</td>
          <td>26,562</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>20.25</td>
          <td>1,562</td>
          <td>24,783.75</td>
        </tr>
    </table>
    <!-- C++ unordered_map -->
    <table>
        <caption>C++ unordered_map (2.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>8</td>
          <td>17</td>
          <td>68</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>10</td>
          <td>14</td>
          <td>27</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>8</td>
          <td>14</td>
          <td>27</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>10</td>
          <td>14</td>
          <td>48</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>9</td>
          <td>14.75</td>
          <td>42.5</td>
        </tr>
    </table>
    <!-- Java HashMap -->
    <table>
        <caption>Java HashMap (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>40</td>
          <td>55</td>
          <td>118</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>26</td>
          <td>51</td>
          <td>76</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>24</td>
          <td>71</td>
          <td>62</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>19</td>
          <td>38</td>
          <td>70</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>27.25</td>
          <td>53.75</td>
          <td>74</td>
        </tr>
    </table>
    <hr>
    <h3>Lookup Time</h3>
    <p>Metric: Data structure search complexity</p>
    <p>Description: The runtime efficiency of hash functions, bucket indexing, and pointer references when searching for data.</p>
    <!-- C++ Vector -->
    <table>
        <caption>C++ Vector (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>3.13</td>
          <td>55.45</td>
          <td>132.35</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>3.2</td>
          <td>51.37</td>
          <td>167.58</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>3.18</td>
          <td>64.25</td>
          <td>169.73</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>3.15</td>
          <td>114.85</td>
          <td>243.54</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>3.165</td>
          <td>71.48</td>
          <td>178.3</td>
        </tr>
    </table>
    <!-- C++ unordered_map -->
    <table>
        <caption>C++ unordered_map (2.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>1.52381</td>
          <td>0.215686</td>
          <td>0.208054</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>0.285714</td>
          <td>0.45098</td>
          <td>0.204698</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>0.238095</td>
          <td>0.464052</td>
          <td>0.208054</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>0.333333</td>
          <td>0.215686</td>
          <td>0.208054</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>0.595238</td>
          <td>0.336601</td>
          <td>0.207215</td>
        </tr>
    </table>
    <!-- Java HashMap -->
    <table>
        <caption>Java HashMap (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1</td>
          <td>0.19565</td>
          <td>0.33548</td>
          <td>0.29431</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>2</td>
          <td>0.15217</td>
          <td>0.2</td>
          <td>0.08026</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>3</td>
          <td>0.34782</td>
          <td>0.07741</td>
          <td>0.08361</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>4</td>
          <td>0.15217</td>
          <td>0.18064</td>
          <td>0.08695</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Average Time</td>
          <td>0.2119525</td>
          <td>0.1983825</td>
          <td>0.1362825</td>
        </tr>
    </table>
    <hr>
    <h3>Cold-Start vs. Warm-Start Execution</h3>
    <p>Metric: System-level execution efficiency and runtime behavior over time.</p>
    <p>Description: Compares Java’s JIT compilation process against C++’s data structure behavior.</p>
    <p>How long does the entire application take to look up 100 courses and print the entire computer science catalog?</p>
    <!-- C++ Vector -->
    <table>
        <caption>C++ Vector (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1-5</td>
          <td>2,865.2</td>
          <td>15,657.2</td>
          <td>35,203.6</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>6-20</td>
          <td>2,877.375</td>
          <td>15,373.3125</td>
          <td>33,179.375</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>21+</td>
          <td>2,804</td>
          <td>16,072.1519</td>
          <td>33,048.81013</td>
        </tr>
        <!-- Average Time -->
        <tr>
          <td>Total Compilation Time (s)</td>
          <td>1.139</td>
          <td>1.93</td>
          <td>1.12</td>
        </tr>
    </table>
    <!-- C++ unordered_map -->
    <table>
        <caption>C++ unordered_map (2.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1-5</td>
          <td>5,365.8</td>
          <td>18,399.4</td>
          <td>37,088.8</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>6-20</td>
          <td>3,814.875</td>
          <td>18,109.1875</td>
          <td>36,529.5</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>21+</td>
          <td>3,812.886076</td>
          <td>18,762.49367</td>
          <td>36,641.37975</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>Total Compilation Time (s)</td>
          <td>1.181</td>
          <td>1.319</td>
          <td>1.277</td>
        </tr>
    </table>
    <!-- Java HashMap -->
    <table>
        <caption>Java HashMap (1.0)</caption>
        <!-- Header Row -->
        <tr>
          <th>Trial</th>
          <th>1,000 entries µs</th>
          <th>5,000 entries µs</th>
          <th>10,000 entries µs</th>
        </tr>
        <!-- Trial 1 -->
        <tr>
          <td>1-5</td>
          <td>265,068.8</td>
          <td>1,116,294</td>
          <td>2,056,289</td>
        </tr>
        <!-- Trial 2 -->
        <tr>
          <td>6-20</td>
          <td>270,041.375</td>
          <td>1,037,444.563</td>
          <td>2,008,267.188</td>
        </tr>
        <!-- Trial 3 -->
        <tr>
          <td>21+</td>
          <td>263,284.8608</td>
          <td>1,026,343.392</td>
          <td>2,008,454.544</td>
        </tr>
        <!-- Trial 4 -->
        <tr>
          <td>Total Compilation Time (s)</td>
          <td>2.059</td>
          <td>1.656</td>
          <td>2.652</td>
        </tr>
    </table>
    <hr>
</div>


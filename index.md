---
layout: page
title: 데이터 과학을 위한 R 알고리즘
---

<img src="fig/ct-unplugged-4th-paradigm-korea.png" width="57%" />

> ### AI is a Superpower {.callout}
>
> "Statistical thinking will one day be as necessary for efficient citizenship as the ability to read and write" Samuel S. Wilks paraphrasing Herbert G. Wells
>


## 학습목차 

- [수식에서 그래프까지](from-math-to-expression.html)
- **[R 알고리즘 코딩](r-algorithm.html)** [^grokking-algorithms] [^grokking-algorihtms-github]
    - [이진검색(Binary Search)](r-binary-search.html)
    - [선택정렬(Selectin Sort)](r-selection-sort.html)
    - [재귀(Recursion)](r-recursion.html)
    - [분할정복(Divide&Conquer) - 퀵정렬(Quick Sort)](r-quick-sort.html)
    - [유클리드 호제법(Euclidean Algorithm)-최대공약수](r-euclid-algorithm.html)
    - [요세푸스 문제(Josephus Problem)](r-josephus-problem.html)
- **[확률의 역사](r-history-of-probability.html)**
    - [생일문제(Birthday Problem)](r-birthday-problem.html) 
    - [몬티홀 문제(Monty Hall Problem)](r-monty-hall-problem.html) 
    - [최초 성공 (기하분포)](r-geometric-distribution.html) 
    - [쿠폰 수집가 문제(Coupon Collector Problem)](r-coupon-collector-problem.html) 
    - [캔디 판매(Selling Candy Problem)](r-selling-candy-problem.html) 
    - [확률 모의실험(R 연습문제 중심)](r-probability-exercise.html) 
    - [상트페테르부르크의 역설 (St. Petersburg paradox)](r-petersburg-paradox.html) 
    - [산타 선물 문제 (교란순열, Derangement)](r-hat-derangement.html) 
- **문제 해결**    
    - [최단 도시 연결(Minimal Spanning Tree)](r-minimal-spanning-tree.html) 
    - [지도 색칠 문제(Graph Coloring Problem)](r-graph-coloring-problem.html) 
- **수학 문제**
    - [원주율($\pi$)](r-monte-carlo-pi.html) 
    - [황금비(Golden Ratio)](r-golden-ratio.html)
- **최적화(Optimization)**
    - [R 조합수학(Combinatorics)](ml-combinatorics.html)        
    - [최대우도법(Maximum Likelihood Estimation, MLE)](r-mle-normal.html) 
- **[몬테카를로 모의실험(Monet-Carlo Simulation)](r-statistical-simulation.html)**
    - [역산법(Inverse Trasnfomation Sampling)](inverse-transformation-sampling.html)
    - [기각법(Acceptance-Rejection Sampling)](acceptance-rejection-sampling.html)


[^grokking-algorithms]: [Aditya Y. Bhargava(2016, "Grokking Algorithms - An illustrated guide for programmers and other curious people", Manning Publications](https://www.manning.com/books/grokking-algorithms)

[^grokking-algorihtms-github]: [Code for the book Grokking Algorithms](https://github.com/egonSchiele/grokking_algorithms)

> ### 빅오 표기법 {.callout}
>
> - $\mathcal{O}(log(n))$: 로그소요 시간, 예를 들어 이진검색(Binary Search)
> - $\mathcal{O} (n)$: 선형소요 시간, 단순 검색(Simple Search)
> - $\mathcal{O} (n \times log(n))$: 빠른 검색 알고리즘 퀵정렬(quicksort)
> - $\mathcal{O}(n^2)$: 느린 정렬 알고리즘, 선택정렬(selection sort)
> - $\mathcal{O}(n!)$. 정말 느린 알고리즘, 외판원 여행 문제(traveling salesperson problem)

### xwMOOC 오픈 교재

- [컴퓨터 과학 언플러그드](http://statkclee.github.io/website-csunplugged/)  
- [리보그](http://reeborg.xwmooc.org)  
     - [러플](http://rur-ple.xwmooc.org)  
- [파이썬 거북이](http://swcarpentry.github.io/python-novice-turtles/index-kr.html)  
- [정보과학을 위한 파이썬](http://python.xwmooc.org)  
- [소프트웨어 카펜트리 5.3](http://swcarpentry.xwmooc.org)
- [IoT 오픈 하드웨어(라즈베리 파이)](http://statkclee.github.io/raspberry-pi)
    - [$100 오픈 컴퓨터](http://computer.xwmooc.org/)   
    - [$100 오픈 슈퍼컴퓨터](http://computers.xwmooc.org/)
- **데이터 과학**
    - [R 데이터과학](http://statkclee.github.io/data-science)
    - [R 팩키지](http://r-pkgs.xwmooc.org/)
    - [R 도커](http://statkclee.github.io/r-docker/)
    - [통계적 사고](http://think-stat.xwmooc.org/)
    - [시각화](https://statkclee.github.io/viz/)
- **기계학습, 딥러닝, 인공지능**
    - [기계학습](http://statkclee.github.io/ml)
    - [고생대 프로젝트](http://statkclee.github.io/trilobite)
    - [xwMOOC 딥러닝과 $H_2 O$](https://statkclee.github.io/deep-learning/)
    - [R 병렬 프로그래밍](https://statkclee.github.io/parallel-r/)
- [기호 수학(Symbolic Math)](http://sympy.xwmooc.org/)
- [선거와 투표](http://statkclee.github.io/politics)


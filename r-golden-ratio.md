# 데이터 과학을 위한 R 알고리즘
`r Sys.Date()`  



## 1. 황금비 (Golden Ratio) 정의 {#golden-ratio}


황금비(Golden ratio)는 어떤 두 수의 비율이 그 합과 두 수중 큰 수의 비율과 같도록 하는 비율로, 
근사값이 1.618... 같이 정의되는 무리수이다. 
기하학적으로 해석하면 더 큰 $a$와 $a+b$에 대한 비율이 $a$와 $b$에 대한 비율과 같다는 것으로 
하나의 선분에 대해서도 성립하고, 직사각형 면적에 대해서도 성립한다.

수학적으로 정의와 기하학적 의미는 다음과 같다.

<img src="fig/golden-ratio.png" alt="기하적인 의미 - 황금비" width="57%" />

이를 수학적으로 표현하면 다음과 같다. 그리고, 황금비를 $\varphi$로 표기한다.

$$ \frac{a + b}{a}  = \frac{a}{b} \overset{\underset{\mathrm{def}}{}}{=} \varphi$$

### 1.1 황금비는 얼마인가? {#golden-ratio-root}

황금비가 무리수라는 것이 알려져 있다. 이제 황금비가 얼마인지 수식을 풀어보자.

$$\varphi \overset{\underset{\mathrm{def}}{}}{=} \frac{a + b}{a}  = \frac{a}{b}$$

양변을 $ab$로 곱해주고 정리하면 다음과 같다.

$$\frac{a + b}{a} \times ab  = \frac{a}{b} \times ab$$

$$ab + b^2 = a^2$$

이제 앞서 정의한 황금비 $\frac{a}{b} \overset{\underset{\mathrm{def}}{}}{=} \varphi$에 맞춰 정리하기 위해서 양변을 $b^2$으로 나눠주고 $\varphi$ 값으로 정리한다.

$$ \frac {ab + b^2}{b^2} = \frac{a^2}{b^2}$$

$$\bigg(\frac {a}{b} \bigg)  + 1 = \bigg(\frac{a}{b} \bigg)^2$$

$$\varphi  + 1 = \varphi^2$$

이제 2차 방정식으로 정리하고 나서 풀어내면 방정식의 해를 구할 수 있고, 따라서 황금비를 구할 수 있다.

$$\varphi^2 - \varphi  - 1 = 0$$


$$\varphi = \frac{1+\sqrt{5}}{2} = 1.6180339887\ldots$$


### 1.2 컴퓨터를 활용한 황금비 계산 {#golden-ratio-root-with-computers}

R을 설치하면 `stats` 팩키지 내부에 `unitroot` 함수가 있어 방정식의 근을 찾을 수 있다.
황금비 함수를 `phi^2 - phi -1` 정의하고 나서 `unitroot` 함수에 근을 찾는 구간을 지정하면 근을 구할 수 있다.

이를 `curve` 함수로 황금비 함수를 시각화하고, 해가 존재하는 선을 `abline` 함수로 긋고 나서,
`unitroot`로 찾아진 근을 `points` 함수로 점모양(`pch=16`), 두배 크기(`cex = 2`), 색상은 푸른색(`col="blue"`)으로 지정하여 
시각화한다.


~~~{.r}
# 1. 황금비 
## 1.1. 황금비 함수 정의
golden_ratio <- function (phi) {
    phi^2 - phi -1    
}

## 1.2. 황금비 근찾기
gr_root <- uniroot(golden_ratio, c(0, 2))$root

## 1.3. 황금비 근 시각화
curve(golden_ratio(x), -2, 2)
abline(h = 0, lty = 3)
points(gr_root, 0, pch = 16, cex = 2, col="blue")
~~~

<img src="fig/golden-ratio-plot-1.png" style="display: block; margin: auto;" />

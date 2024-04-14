# GPIO(General Purpose Input Output)란

- MCU가 주변장치와 통신하기 위해 범용으로 사용되는 입출력 포트.

## 회로 기초
1. 전류는 전압이 높은 곳에서 낮은 곳으로 흐른다. 

## PULL UP & PULL DOWN
- GPIO output 모드에서는 크게 의미가 없다. GPIO Input 모드에서 중요. Open-drain 구성에서만 유효하다.
- floating : '0'인지 '1'인지 알 수 없는 상태.
- PULL UP : 저항을 스위치 위쪽에 달아서 스위치가 닫히면 핀에 전압이 걸리게하는 회로, 전압을 위로 끌어 당기다.
- PULL DOWN : 저항을 스위치 아래에 달아서 스위치가 닫히면 저항으로 인해 전류가 그라운드로 흐르지 않고 핀에 흐른다. 전압을 아래로 끌어 당기다. 

## GPIO output level이란?
High 혹은 Low로 설정할 수 있다. GPIO의 초기값을 설정할 수 있다. 
최초 값을 정해주는 것이다. High면 초기값이 해당 핀에 3.3V가 통하는 상태. Low면 초기값이 해당 핀에 0V인 상태로 이해할 수 있다.

## Maximum Output Speed
디지털 신호에서 0과 1로 값을 구분하지만 사실은 0에서 1이 되는데 아주 작은 시간이 필요하다. 이때, 그 걸리는 시간을 설정할 수 있다. 
(High / Low)

## BJT, MOSFET 회로

## OPEN DRAIN
스위치를 쇼트시키면, GND와 연결되어 0V Low Level 출력됨. Open 되면 floating 상태. 

## 고추건조기 설정에 따른 값
- GPIO_LED
    - output level 
        - high : 양쪽에서 3.3V가 걸리므로 LED에 전류가 흐르지 않음
        - low : 한쪽에서 3.3V가 걸리고 반대쪽은 0V이므로 전류가 흐름. 
    - GPIO Pull-up/Pull-down : 
        - Pull-up, Pull-down 똑같음. 
- GPIO_SWITCH (Input Mode)
    - GPIO Pull-Up : 저항이 위에 달려있기 때문에 스위치를 열고 있을 때 핀에 전압이 걸린다. 즉 핀의 상태를 읽을 때 High 값이 읽힌다. 


# HAL 라이브러리 없이 GPIO 제어하기 

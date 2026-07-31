**Volume 14 Mobile Manipulator Architecture**

# Chapter 6. Mobile Base Integration

## 6.1 AMR Manipulator Power Sharing

![](images/image1.png){width="7.268055555555556in" height="7.268055555555556in"}

# 06_01 AMR-매니퓰레이터 전력 공유(AMR Manipulator Power Sharing)

AMR-매니퓰레이터 전력 공유(AMR Manipulator Power Sharing)는 현대 모바일 로봇(Mobile Robot), 자율 이동 매니퓰레이터(Autonomous Mobile Manipulator), 물류 자동화 시스템(Logistics Automation System), 산업용 검사 로봇(Industrial Inspection Robot), 서비스 로봇(Service Robot), 스마트 제조 플랫폼(Intelligent Manufacturing Platform), 그리고 피지컬 AI(Physical AI) 시스템에서 매우 중요한 아키텍처 개념이다.

로봇 플랫폼이 단순한 이동 장비(Mobile Platform)에서 자율 작업 스테이션(Autonomous Workstation)으로 발전함에 따라, 자율이동로봇(AMR)과 로봇 매니퓰레이터(Robot Manipulator)를 하나의 플랫폼으로 통합하는 사례가 증가하고 있다. 그러나 이러한 통합은 전력 생성(Power Generation), 전력 분배(Power Distribution), 전력 관리(Power Management), 에너지 최적화(Energy Optimization), 시스템 수준 에너지 협조(System-Level Energy Coordination)와 같은 새로운 과제를 발생시킨다.

효율적인 전력 공유 구조는 이동(Mobility)과 조작(Manipulation) 기능이 동일한 배터리(Battery) 자원을 사용하면서도 운용 시간(Operating Time), 신뢰성(Reliability), 안전성(Safety), 임무 수행 능력(Mission Performance)을 최대화할 수 있도록 지원한다.

과거에는 AMR과 산업용 매니퓰레이터가 서로 독립적인 시스템으로 개발되었다. 이동 로봇은 주행(Navigation)과 운송(Transportation)에 집중하였고, 로봇 암(Robot Arm)은 공장 전력망(Industrial Power Infrastructure)에 연결된 고정형 설비로 사용되었다. 그러나 최근에는 하나의 로봇이 이동과 조작을 동시에 수행하는 모바일 매니퓰레이터(Mobile Manipulator)가 빠르게 확산되고 있다.

이러한 구조에서는 로봇 베이스(Robot Base)와 매니퓰레이터가 하나의 배터리를 공유해야 한다. 따라서 모든 전력 소비가 배터리 사용 시간에 직접적인 영향을 미친다.

AMR 매니퓰레이터 시스템의 주요 전력 소비원은 다음과 같다.

주행 모터(Drive Motor)는 차량 이동을 담당하며 일반적으로 가장 큰 연속 부하(Continuous Load)를 형성한다.

조향 액추에이터(Steering Actuator)는 4륜 조향(Four-Wheel Steering)이나 전방향 이동(Omnidirectional Motion) 플랫폼에서 상당한 전력을 소비한다.

로봇 암 구동기(Manipulator Actuator)는 작업 중 높은 순간 전력(Peak Power)을 요구한다.

LiDAR, 카메라(Camera), 레이더(Radar), GNSS, IMU와 같은 센서(Sensor)도 지속적으로 전력을 소비한다.

GPU, 엣지 컴퓨터(Edge Computer), AI 가속기(AI Accelerator)는 자율주행 및 AI 추론을 위해 상당한 전력을 요구한다.

무선 통신(Wireless Communication), 안전 제어기(Safety Controller), 조명(Lighting), 기타 주변 장치(Auxiliary Equipment) 역시 전체 에너지 소비에 기여한다.

전력 공유 시스템의 가장 중요한 목적은 제한된 에너지를 여러 하위 시스템(Sub-System)에 효율적으로 분배하는 것이다. 시스템은 필수 기능(Essential Function)을 항상 유지하면서도 전체 임무 성능을 최적화해야 한다.

일반적으로 전력 구조는 중앙 배터리 시스템(Central Battery System)에서 시작된다. 최근에는 리튬인산철 배터리(Lithium Iron Phosphate, LFP)가 안전성(Safety), 긴 수명(Long Cycle Life), 열 안정성(Thermal Stability), 경제성(Cost Effectiveness) 때문에 가장 널리 사용된다.

고에너지 밀도(High Energy Density)가 필요한 경우에는 리튬 니켈 망간 코발트 배터리(Lithium Nickel Manganese Cobalt, NMC)를 사용하기도 한다.

배터리 용량(Battery Capacity)은 운용 시간, 차량 중량, 적재 능력, 충전 전략, 경제성에 직접적인 영향을 준다.

배터리는 일반적으로 DC 버스(DC Bus)를 통해 전체 시스템에 전력을 공급한다.

소형 실내 AMR은 24V 시스템을 사용하는 경우가 많으며, 중대형 실외 AMR은 48V 시스템을 가장 많이 사용한다.

고출력 플랫폼에서는 72V 이상의 구조도 사용된다.

특히 사용자가 개발 중인 실내·실외 AMR 플랫폼에서는 48V 기반 전력 아키텍처가 가장 현실적인 선택이다. 48V는 효율(Efficiency), 안전성(Safety), 부품 수급(Component Availability), 전력 공급 능력(Power Delivery Capability)의 균형이 우수하기 때문이다.

전력 분배 장치(Power Distribution Unit, PDU)는 전체 전력 흐름을 관리하는 중심 장치이다.

PDU는 주행 시스템, 매니퓰레이터, 센서, 컴퓨터, 통신 장비, 안전 장치에 전력을 분배하며 과전류(Overcurrent), 단락(Short Circuit), 과전압(Overvoltage)으로부터 시스템을 보호한다.

주행 시스템(Propulsion System)은 이동 중 가장 큰 전력을 소비한다.

전력 소비량은 차량 중량(Vehicle Weight), 적재 하중(Payload), 가속도(Acceleration), 노면 저항(Rolling Resistance), 경사도(Slope), 이동 속도(Speed)에 따라 결정된다.

실내 물류 AMR은 상대적으로 적은 전력을 사용하지만, 실외 자율주행 플랫폼은 훨씬 큰 전력을 요구한다.

매니퓰레이터의 전력 소비 특성은 주행 시스템과 다르다.

주행 시스템은 비교적 일정한 부하를 갖지만, 매니퓰레이터는 순간적으로 매우 높은 전력을 요구하는 동적 부하(Dynamic Load) 특성을 가진다.

관절 모터(Joint Motor)는 가속, 감속, 물체 인양(Lifting), 힘 제어(Force Control), 궤적 추종(Trajectory Tracking) 과정에서 높은 전력을 소비한다.

AMR이 이동하면서 동시에 작업을 수행하는 경우 전력 공유는 더욱 중요해진다.

예를 들어 이동 중 검사(Mobile Inspection), 이동 중 집기(Pick-and-Move), 이동 중 CAD2SCAN 스캔과 같은 작업에서는 주행과 조작이 동시에 이루어진다.

이 경우 순간 최대 전력(Peak Power)이 크게 증가할 수 있으며, 적절한 전력 관리가 없으면 배터리 전압 강하(Voltage Sag), 시스템 불안정(System Instability), 배터리 열화(Battery Degradation)가 발생할 수 있다.

이를 해결하기 위해 동적 전력 할당(Dynamic Power Allocation) 기법이 사용된다.

에너지 관리 시스템(Energy Management System)은 현재 임무(Mission), 배터리 상태(Battery Condition), 작업 우선순위(Task Priority)에 따라 각 하위 시스템에 공급되는 전력을 조정한다.

예를 들어 무거운 물체를 들어 올릴 때는 차량 속도를 제한하고, 장거리 이동 시에는 매니퓰레이터를 대기 상태(Standby Mode)로 전환하여 에너지를 절약할 수 있다.

최대 전력 관리(Peak Power Management)는 매우 중요한 기술이다.

주행 모터와 매니퓰레이터가 동시에 최대 출력을 요구하면 배터리와 전력 시스템에 큰 스트레스가 발생한다.

지능형 전력 관리 알고리즘(Intelligent Power Management Algorithm)은 이러한 부하를 시간적으로 분산시켜 전체 시스템의 안정성을 유지한다.

전력 전자 장치(Power Electronics)는 효율적인 전력 공유를 가능하게 한다.

DC-DC 컨버터(DC-DC Converter)는 배터리 전압을 필요한 전압으로 변환한다.

일반적으로 다음과 같은 전압 도메인(Voltage Domain)이 사용된다.

48V : 구동 모터, 조향 모터, 대형 액추에이터

24V : 산업용 센서, PLC, 일부 매니퓰레이터

12V : 카메라, 통신 장비

5V : MCU, 임베디드 장치, 저전력 센서

매니퓰레이터의 에너지 소비는 동작 계획(Motion Planning)에 의해 크게 영향을 받는다.

불필요한 가속과 감속을 줄이고 최적 경로(Optimal Trajectory)를 생성하면 상당한 전력 절감 효과를 얻을 수 있다.

회생 에너지(Regenerative Energy Recovery)는 전체 효율을 향상시키는 중요한 기술이다.

감속(Deceleration), 하강(Descending Motion), 제동(Braking) 시 발생하는 에너지를 다시 배터리로 회수할 수 있다.

주행 모터뿐 아니라 일부 서보 모터(Servo Motor)도 회생 제동(Regenerative Braking)을 지원한다.

AI 기반 에너지 관리(AI-Based Energy Management)는 최근 중요한 연구 분야로 떠오르고 있다.

머신러닝(Machine Learning)은 과거 임무 수행 기록, 배터리 상태, 환경 조건, 작업 패턴을 분석하여 최적의 전력 분배 전략을 생성할 수 있다.

배터리 충전 상태(State of Charge, SOC)는 전력 공유의 핵심 입력 정보이다.

SOC가 낮아지면 시스템은 비필수 기능(Non-Essential Function)을 제한하고 핵심 기능(Critical Function)에 에너지를 집중시킨다.

배터리 건강 상태(State of Health, SOH)는 장기적인 전력 관리에 중요하다.

배터리가 노화되면 용량(Capacity)과 출력 능력(Power Capability)이 감소하기 때문에 전력 분배 전략도 이에 맞게 조정되어야 한다.

열 관리(Thermal Management)는 전력 공유와 밀접한 관계가 있다.

배터리, 모터, 인버터(Inverter), GPU, 엣지 컴퓨터는 모두 열을 발생시킨다.

온도가 높아지면 효율이 감소하고 수명이 단축되므로 전력 관리와 열 관리는 통합적으로 설계되어야 한다.

안전 시스템(Safety System)은 항상 가장 높은 우선순위를 가진다.

비상 정지(Emergency Stop), 안전 제어기(Safety Controller), 장애물 감지 센서(Obstacle Detection Sensor), 브레이크 시스템(Brake System)은 배터리가 부족한 상황에서도 반드시 동작해야 한다.

따라서 전력 공유 구조는 항상 안전 예비 전력(Safety Energy Reserve)을 확보해야 한다.

사용자가 개발 중인 실외 AMR 플랫폼처럼 RTX A6000 Ada, Jetson Orin NX, 다중 LiDAR, 다중 카메라를 사용하는 구조에서는 컴퓨팅 전력(Computing Power)이 전체 소비 전력의 상당 부분을 차지한다.

GPU는 자율주행 AI, 검사 AI, CAD2SCAN 분석을 수행하며 수백 와트 수준의 전력을 사용할 수 있다.

따라서 작업 스케줄링(Workload Scheduling), GPU 부하 관리(GPU Load Management), AI 추론 최적화(AI Inference Optimization)가 매우 중요하다.

센서 시스템 역시 상당한 전력을 소비한다.

LiDAR, Stereo Camera, Radar, GNSS RTK, IMU, Force Sensor는 지속적으로 데이터를 생성한다.

상황에 따라 업데이트 주기(Update Rate)를 조정하는 적응형 센싱(Adaptive Sensing)을 적용하면 전력 소비를 줄일 수 있다.

자동 충전 시스템(Automatic Charging System)은 전력 공유 전략과 긴밀하게 연결된다.

배터리 잔량이 임계값 이하로 떨어지면 로봇은 자동으로 충전 스테이션(Charging Station)으로 이동한다.

기회 충전(Opportunity Charging)을 이용하면 짧은 대기 시간에도 에너지를 보충할 수 있어 전체 가동률을 향상시킬 수 있다.

플릿 수준 에너지 관리(Fleet-Level Energy Management)는 다수의 AMR이 운영되는 환경에서 중요하다.

플릿 관리 시스템(Fleet Management System)은 충전 스케줄, 임무 할당, 배터리 사용량을 최적화하여 전체 운영 효율을 극대화한다.

디지털 트윈(Digital Twin)은 전력 공유 설계를 최적화하는 강력한 도구이다.

배터리 동작, 전력 소비, 열 특성, 임무 수행을 가상 환경에서 시뮬레이션하여 최적 구조를 검증할 수 있다.

미래의 AMR 매니퓰레이터 전력 공유 기술은 고에너지 밀도 배터리(Higher Energy Density Battery), 지능형 전력 라우팅(Intelligent Power Routing), AI 기반 에너지 최적화(AI-Driven Energy Optimization), 고효율 전력 전자 장치(High-Efficiency Power Electronics), 에너지 인지형 임무 계획(Energy-Aware Mission Planning) 방향으로 발전할 것이다.

자율 물류(Autonomous Logistics), 스마트 제조(Intelligent Manufacturing), 모바일 조작(Mobile Manipulation), 서비스 로봇(Service Robotics), 피지컬 AI 시대가 도래함에 따라 AMR 매니퓰레이터 전력 공유는 이동(Mobility), 조작(Manipulation), 인지(Perception), 컴퓨팅(Computing), 통신(Communication)을 하나의 에너지 시스템 위에서 조화롭게 운영하게 만드는 핵심 기반 기술(Core Enabling Technology)이 될 것이다. 이는 차세대 모바일 로봇 아키텍처에서 가장 중요한 시스템 설계 요소 중 하나로 자리 잡게 될 것이다.

## 6.2 CAN EtherCAT Integration

![](images/image2.png){width="7.268055555555556in" height="7.268055555555556in"}

# 06_02 CAN-EtherCAT 통합(CAN-EtherCAT Integration)

CAN-EtherCAT 통합(CAN-EtherCAT Integration)은 현대 로봇(Robotics), 산업 자동화(Industrial Automation), 자율이동로봇(Autonomous Mobile Robot, AMR), 모바일 매니퓰레이터(Mobile Manipulator), 자율주행 차량(Autonomous Vehicle), 스마트 제조 시스템(Intelligent Manufacturing System), 그리고 피지컬 AI(Physical AI) 플랫폼에서 가장 중요한 통신 아키텍처(Communication Architecture) 중 하나이다.

로봇 시스템이 점점 더 복잡해지고 분산 구조(Distributed Architecture)로 발전함에 따라, 하나의 플랫폼 내부에서 여러 종류의 통신 프로토콜(Communication Protocol)이 동시에 사용되고 있다. CAN(Controller Area Network)과 EtherCAT(Ethernet for Control Automation Technology)은 현재 산업 현장에서 가장 널리 사용되는 통신 기술이며, 서로 다른 목적과 특성을 가지고 있다.

이 두 기술을 효과적으로 통합하면 결정론적 실시간 제어(Deterministic Real-Time Control)와 안정적인 서브시스템 통신(Sub-System Communication)을 동시에 구현할 수 있으며, 확장성(Scalability), 비용 효율성(Cost Efficiency), 유지보수성(Maintainability), 시스템 신뢰성(System Reliability)을 향상시킬 수 있다.

산업 제어 시스템은 원래 분산 제어 시스템(Distributed Control System)을 구현하기 위해 다양한 필드버스(Fieldbus) 기술을 발전시켜 왔다.

CAN은 자동차 산업(Automotive Industry)에서 시작된 통신 기술이다. 높은 신뢰성(Reliability), 우수한 오류 검출(Error Detection), 전자파 내성(Electromagnetic Immunity), 저비용(Low Cost) 특성 덕분에 산업용 로봇, 의료 장비(Medical Equipment), 농업 기계(Agricultural Machinery), 자율 시스템(Autonomous System)까지 적용 범위가 확대되었다.

반면 EtherCAT은 고속 산업용 이더넷(Industrial Ethernet) 기술로 개발되었다. 기존 필드버스보다 훨씬 높은 대역폭(Bandwidth), 더 정확한 동기화(Synchronization), 더 우수한 실시간 성능(Real-Time Performance)을 제공한다.

현대 로봇은 매우 다양한 통신 요구사항을 가진다.

서보 모터(Servo Motor), 엔코더(Encoder), 힘 센서(Force Sensor), 토크 센서(Torque Sensor), 조인트 제어기(Joint Controller)는 수백 마이크로초(Microsecond) 수준의 고속 동기화가 필요하다.

반면 배터리 관리 시스템(Battery Management System), 전력 분배 장치(Power Distribution Unit), 환경 센서(Environmental Sensor), 진단 장치(Diagnostic Module)는 상대적으로 낮은 속도의 통신으로도 충분하다.

CAN-EtherCAT 통합은 이러한 요구사항을 효율적으로 분리하여 각 프로토콜의 장점을 최대한 활용하도록 한다.

CAN은 신뢰성(Reliability), 내결함성(Fault Tolerance), 구현 용이성(Implementation Simplicity)을 우선시하는 분산 장치 통신에 적합하다.

CAN은 메시지 기반(Message-Based Architecture) 구조를 사용한다. 여러 장치가 하나의 버스(Bus)를 공유하면서도 우선순위 기반 통신(Priority-Based Communication)을 수행할 수 있다.

이러한 특성 때문에 CAN은 배터리 시스템, 전력 전자 장치(Power Electronics), 안전 제어기(Safety Controller), 환경 모니터링(Environmental Monitoring), 충전 시스템(Charging System)에 널리 사용된다.

반면 EtherCAT은 정밀 모션 제어(Motion Control)를 위해 설계되었다.

EtherCAT은 분산 클록(Distributed Clock), 서브 마이크로초 동기화(Sub-Microsecond Synchronization), 고속 순환 통신(High-Speed Cyclic Communication), 대규모 분산 제어(Large-Scale Distributed Control)를 지원한다.

따라서 서보 드라이브(Servo Drive), 로봇 매니퓰레이터(Robot Manipulator), 정밀 자동화 장비(Precision Automation Equipment), 머신 비전(Machine Vision), 동기화 액추에이터(Synchronized Actuator)에 적합하다.

CAN-EtherCAT 통합은 일반적으로 계층형 통신 구조(Hierarchical Communication Architecture)를 형성한다.

EtherCAT은 실시간 제어 백본(Real-Time Motion Backbone)의 역할을 수행한다.

CAN은 서브시스템 네트워크(Sub-System Network)의 역할을 수행한다.

예를 들어 모바일 매니퓰레이터에서는 다음과 같은 구성이 가능하다.

EtherCAT 네트워크는 다음 장치를 연결한다.

주행 서보 드라이브(Drive Servo Drive)

조향 액추에이터(Steering Actuator)

로봇 암 조인트(Robot Arm Joint)

힘 제어 시스템(Force Control System)

고속 센서(High-Speed Sensor)

CAN 네트워크는 다음 장치를 연결한다.

배터리 관리 시스템(BMS)

전력 분배 장치(PDU)

충전기(Charger)

조명 장치(Lighting Module)

환경 센서(Environmental Sensor)

진단 장치(Diagnostic Device)

전체 통신 구조는 중앙 제어기(Central Controller)를 중심으로 구성된다.

중앙 제어기는 산업용 PC(Industrial PC), 엣지 컴퓨터(Edge Computer), 실시간 제어기(Real-Time Controller) 형태로 구현될 수 있다.

EtherCAT Master는 EtherCAT 네트워크 전체를 관리한다.

주기적으로(Cyclic Communication) 슬레이브(Slave) 장치와 데이터를 교환하며 위치(Position), 속도(Velocity), 토크(Torque), 센서 데이터(Sensor Data)를 수집한다.

CAN 네트워크는 다르게 동작한다.

중앙 제어 방식이 아니라 메시지 우선순위(Message Priority)에 따라 장치들이 스스로 데이터를 전송한다.

이 구조는 통신 효율성과 내결함성을 향상시킨다.

CAN-EtherCAT 통합에서 가장 중요한 장치 중 하나는 게이트웨이(Gateway)이다.

CAN-EtherCAT 게이트웨이는 두 네트워크 사이의 번역기(Translator) 역할을 수행한다.

게이트웨이는 다음을 변환한다.

데이터 구조(Data Structure)

주소 체계(Addressing Scheme)

통신 포맷(Communication Format)

타이밍 구조(Timing Architecture)

게이트웨이는 전용 하드웨어(Dedicated Hardware), 산업용 컨트롤러(Industrial Controller), 임베디드 프로세서(Embedded Processor), 소프트웨어 서비스(Software Service) 형태로 구현될 수 있다.

데이터 매핑(Data Mapping)은 CAN-EtherCAT 통합의 핵심 기술이다.

CAN 장치에서 생성된 데이터는 EtherCAT 프로세스 데이터(Process Data)로 변환되어야 한다.

EtherCAT 제어 명령 역시 CAN 메시지로 변환되어야 한다.

예를 들어 배터리 관리 시스템이 CAN을 통해 다음 정보를 제공한다고 가정할 수 있다.

배터리 전압(Battery Voltage)

배터리 전류(Battery Current)

배터리 온도(Battery Temperature)

충전 상태(State of Charge)

이상 상태(Fault Status)

게이트웨이는 이 정보를 EtherCAT 변수(Process Variable)로 변환한다.

이후 모션 제어기(Motion Controller)는 실시간 배터리 상태를 고려하여 주행 및 작업 계획을 최적화할 수 있다.

전력 분배 장치 역시 CAN 네트워크를 통해 다음 정보를 제공할 수 있다.

전류(Current)

회로 차단기 상태(Circuit Breaker Status)

온도(Thermal Information)

고장 정보(Fault Information)

이 정보는 EtherCAT 환경으로 통합되어 중앙 모니터링(Central Monitoring)이 가능해진다.

모바일 로봇은 CAN-EtherCAT 통합의 대표적인 적용 사례이다.

자동차 계열 부품은 대부분 CAN 기반이다.

배터리

조향 제어기

조명 시스템

충전 시스템

차량 제어기

반면 로봇 암은 대부분 EtherCAT 기반이다.

서보 드라이브

엔코더

토크 센서

힘 센서

조인트 컨트롤러

따라서 모바일 매니퓰레이터는 자연스럽게 CAN과 EtherCAT을 동시에 사용하게 된다.

안전 시스템(Safety System)에서도 통합이 중요하다.

현대 로봇은 다음과 같은 안전 기능을 포함한다.

비상 정지(Emergency Stop)

안전 라이다(Safety LiDAR)

충돌 감지(Collision Detection)

안전 토크 오프(Safe Torque Off, STO)

안전 PLC(Safety PLC)

일부 장치는 CANopen Safety를 사용하고, 일부 장치는 FSoE(Fail Safe over EtherCAT)를 사용한다.

CAN-EtherCAT 통합은 이질적인 안전 네트워크(Heterogeneous Safety Network)를 하나의 안전 아키텍처로 통합한다.

동기화(Synchronization)는 기술적으로 매우 중요한 문제이다.

EtherCAT은 매우 정확한 분산 클록을 지원하지만, 일반 CAN은 이러한 기능이 없다.

따라서 게이트웨이는 타임스탬프(Time Stamp), 버퍼(Buffer), 스케줄링 알고리즘(Scheduling Algorithm)을 사용하여 시간 차이를 보정해야 한다.

대역폭 관리(Bandwidth Management)도 중요하다.

EtherCAT은 CAN보다 훨씬 높은 데이터 전송 능력을 가진다.

대량 데이터를 CAN으로 전송할 경우 병목 현상(Bottleneck)이 발생할 수 있다.

이를 해결하기 위해 다음 기술이 사용된다.

필터링(Filtering)

데이터 집계(Data Aggregation)

이벤트 기반 통신(Event-Driven Communication)

우선순위 관리(Priority Management)

진단 기능(Diagnostics)은 CAN-EtherCAT 통합의 또 다른 장점이다.

두 네트워크에서 수집되는 통신 오류, 장치 상태, 동기화 품질, 네트워크 상태를 중앙에서 관리할 수 있다.

이를 통해 유지보수 효율성과 시스템 가시성(System Visibility)이 향상된다.

CANopen과 EtherCAT 표준은 상호 운용성(Interoperability)을 높인다.

표준 장치 프로파일(Device Profile)과 객체 사전(Object Dictionary)을 사용하면 제조사가 달라도 장치 통합이 쉬워진다.

최근에는 사이버보안(Cybersecurity)의 중요성이 증가하고 있다.

게이트웨이는 네트워크 경계(Network Boundary)가 되므로 보안상 매우 중요한 위치를 차지한다.

인증(Authentication)

암호화(Encryption)

접근 제어(Access Control)

침입 탐지(Intrusion Detection)

기능이 필요하다.

디지털 트윈(Digital Twin)은 CAN과 EtherCAT에서 수집된 데이터를 통합하여 가상 시스템(Virtual System)을 구축한다.

이를 통해 시뮬레이션(Simulation), 상태 분석(Condition Analysis), 성능 최적화(Performance Optimization), 예지보전(Predictive Maintenance)을 수행할 수 있다.

인공지능(AI)은 두 네트워크의 데이터를 동시에 활용한다.

EtherCAT에서 수집된 모터 데이터(Motor Data)

CAN에서 수집된 배터리 데이터(Battery Data)

환경 정보(Environmental Data)

진단 정보(Diagnostic Data)

를 통합 분석하여 이상 감지(Anomaly Detection), 예지보전, 에너지 최적화(Energy Optimization)를 수행할 수 있다.

대규모 시스템에서는 여러 개의 CAN 네트워크와 EtherCAT 네트워크가 동시에 존재할 수 있다.

지능형 공장(Intelligent Factory), 물류 센터(Logistics Center), AMR 플릿(Fleet) 환경에서는 계층형 게이트웨이(Hierarchical Gateway Architecture)가 사용된다.

미래의 CAN-EtherCAT 통합 기술은 더 높은 상호 운용성(Interoperability), 더 빠른 게이트웨이 성능(Higher Gateway Performance), 향상된 사이버보안(Enhanced Cybersecurity), AI 기반 통신 최적화(AI-Assisted Communication Optimization), 클라우드 연동(Cloud Integration) 방향으로 발전할 것이다.

로봇이 자율화(Autonomy), 지능화(Intelligence), 연결성(Connectivity)을 강화할수록 CAN-EtherCAT 통합은 필수적인 기반 기술(Core Enabling Technology)이 될 것이다. 특히 실내·실외 AMR, 모바일 매니퓰레이터, 자율주행 로봇, 검사 로봇, 물류 로봇, 피지컬 AI 플랫폼에서는 CAN의 신뢰성과 EtherCAT의 초고속 실시간 제어 능력을 동시에 활용하는 통합 통신 아키텍처가 차세대 로봇 시스템의 표준 구조로 자리잡게 될 것이다.

## 6.3 Dynamic Load Compensation

![](images/image3.png){width="7.268055555555556in" height="7.268055555555556in"}

# 06_03 동적 하중 보상(Dynamic Load Compensation)

동적 하중 보상(Dynamic Load Compensation)은 현대 로봇(Robotics), 자율이동 매니퓰레이터(Autonomous Mobile Manipulator), 산업 자동화 시스템(Industrial Automation System), 협동로봇(Collaborative Robot), 자율주행 차량(Autonomous Vehicle), 스마트 제조 시스템(Intelligent Manufacturing System), 그리고 피지컬 AI(Physical AI) 플랫폼에서 가장 중요한 핵심 기술 중 하나이다.

로봇이 점점 더 빠르고 강력해지며 높은 수준의 자율성을 갖게 되면서, 움직임에 의해 발생하는 동적 힘(Dynamic Force)은 위치 오차(Position Error), 진동(Vibration), 불안정성(Instability), 구조 응력(Structural Stress), 에너지 소비(Energy Consumption), 제어 성능 저하(Control Performance Degradation)의 주요 원인이 되고 있다.

동적 하중 보상은 이러한 힘을 실시간으로 예측(Prediction), 추정(Estimation), 보상(Compensation), 제어(Control)하기 위한 모델링(Modeling), 센싱(Sensing), 추정 알고리즘(Estimation Algorithm), 제어 기법(Control Technique)의 집합을 의미한다.

이상적인 로봇 시스템에서는 액추에이터(Actuator)가 원하는 궤적(Trajectory)을 수행하기 위해 정확한 힘(Force)과 토크(Torque)를 생성해야 한다. 그러나 실제 환경에서는 지속적으로 변화하는 동적 조건(Dynamic Condition)이 존재한다.

질량(Mass)이 가속되면 관성력(Inertial Force)이 발생한다. 회전 부품(Rotating Component)은 원심력(Centrifugal Force)과 코리올리 힘(Coriolis Force)을 발생시킨다. 페이로드(Payload)의 변화는 시스템 동특성(System Dynamics)을 변경한다. 노면 불규칙성(Ground Irregularity)은 외란(Disturbance)을 발생시키고, 구조 유연성(Structural Flexibility)은 진동을 유발한다.

이러한 모든 요소는 로봇 시스템에 동적 하중을 발생시키며, 이를 적절히 보상하지 않으면 정밀도(Accuracy)와 안정성(Stability)이 크게 저하된다.

동적 하중은 질량이 가속도를 받을 때 발생한다. 뉴턴의 운동 법칙(Newtonian Mechanics)에 따르면 힘은 질량과 가속도의 곱으로 표현된다.

로봇이 가속(Acceleration), 감속(Deceleration), 방향 전환(Direction Change), 물체 인양(Lifting), 조작(Manipulation), 비포장 지형 주행(Rough Terrain Driving)을 수행할 때마다 동적 힘이 생성된다.

이 힘은 조인트(Joint), 링크(Link), 베어링(Bearing), 감속기(Gearbox), 바퀴(Wheel), 서스펜션(Suspension), 차체 구조물(Structural Frame)을 통해 전달된다.

동적 하중 보상은 이러한 힘으로 인해 발생하는 오차를 최소화하는 기술이다.

모바일 로봇에서는 다양한 동적 하중 발생 요인이 존재한다.

차량 가속은 종방향 관성력(Longitudinal Inertial Force)을 생성한다.

조향(Steering)은 횡방향 하중(Lateral Load)을 생성한다.

울퉁불퉁한 노면은 수직 충격(Vertical Impact)을 발생시킨다.

페이로드 이동은 무게 중심(Center of Gravity)을 변화시킨다.

매니퓰레이터 동작은 추가적인 힘과 모멘트(Moment)를 발생시킨다.

바람(Wind), 충돌(Collision), 지면 불균형(Surface Irregularity)과 같은 환경 요소도 외란으로 작용한다.

동적 하중의 영향은 로봇이 커지고 빨라질수록 더욱 커진다.

실험실의 소형 로봇은 동적 효과가 거의 무시될 수 있지만, 수백 kg의 하중을 적재한 실외 AMR은 상당한 관성력을 생성한다.

특히 사용자가 개발 중인 500kg\~1000kg Payload급 실외 AMR과 800kg 이상의 Heavy Platform에서는 동적 하중 보상이 매우 중요한 설계 요소가 된다.

동적 하중 보상의 핵심은 동역학 모델(Dynamic Model)이다.

엔지니어는 질량(Mass), 관성(Inertia), 힘(Force), 토크(Torque), 속도(Velocity), 가속도(Acceleration), 외란(Disturbance) 사이의 관계를 수학적으로 모델링한다.

이 모델은 로봇이 특정 제어 입력(Control Input)에 대해 어떻게 반응할 것인지를 예측하는 기반이 된다.

강체 동역학(Rigid Body Dynamics)은 가장 기본적인 모델링 방법이다.

각 구성 요소를 강체(Rigid Body)로 가정하고, 관성(Inertia), 중력(Gravity), 마찰(Friction), 외력(External Force)을 고려하여 운동 방정식(Motion Equation)을 구성한다.

질량 특성(Mass Property)은 동적 보상에서 매우 중요하다.

모든 부품은 질량, 무게 중심, 관성 모멘트(Moment of Inertia)를 가진다.

이 정보는 힘이 시스템 내부에서 어떻게 분포되는지를 결정한다.

특히 모바일 매니퓰레이터는 물체를 집고 놓을 때마다 질량 분포가 변하므로 정확한 질량 모델이 필요하다.

무게 중심 추정(Center of Gravity Estimation)은 또 다른 핵심 기술이다.

물체를 들어 올리거나 위치를 변경하면 전체 시스템의 무게 중심이 이동한다.

이는 차량 안정성(Stability Margin), 휠 하중(Wheel Load), 서스펜션 거동(Suspension Behavior), 액추에이터 부하(Actuator Load)에 영향을 미친다.

따라서 실시간 무게 중심 추정 알고리즘이 사용된다.

매니퓰레이터 동역학(Manipulator Dynamics)은 더욱 복잡하다.

하나의 조인트 움직임이 다른 조인트에 영향을 미치는 결합 효과(Coupling Effect)가 존재한다.

원심력(Centrifugal Force), 코리올리 힘(Coriolis Force), 중력 하중(Gravity Load), 상호작용 토크(Interaction Torque)가 동시에 발생한다.

고급 제어기는 이러한 요소를 실시간으로 계산하여 보상한다.

중력 보상(Gravity Compensation)은 가장 기본적인 동적 보상 방식이다.

모든 로봇 암은 자신의 무게와 페이로드의 무게를 지속적으로 지탱해야 한다.

제어기는 필요한 중력 토크(Gravity Torque)를 미리 계산하고 보상 명령(Compensation Command)을 생성한다.

관성 보상(Inertia Compensation)은 가속에 의해 발생하는 힘을 보상한다.

가속 시 필요한 추가 토크를 미리 계산하여 제어 입력에 포함시킴으로써 추종 오차(Tracking Error)를 줄일 수 있다.

코리올리 보상(Coriolis Compensation)과 원심력 보상(Centrifugal Compensation)은 고속 동작에서 매우 중요하다.

특히 6축 이상의 산업용 매니퓰레이터와 고속 검사 로봇에서는 이러한 힘을 무시할 수 없다.

모바일 매니퓰레이터는 차량과 로봇 암이 서로 영향을 주기 때문에 더욱 복잡하다.

로봇 암의 움직임은 차량 안정성에 영향을 준다.

차량의 가속과 진동은 매니퓰레이터 정밀도에 영향을 준다.

따라서 차량과 매니퓰레이터를 통합적으로 고려하는 동적 보상이 필요하다.

실외 AMR에서는 서스펜션 시스템(Suspension System)이 중요한 역할을 한다.

험지(Terrain)에서 발생하는 충격과 진동은 센서, 매니퓰레이터, 카메라의 성능을 저하시킬 수 있다.

따라서 서스펜션 상태(Suspension State)를 추정하고 이를 보상 모델에 포함하는 것이 중요하다.

진동 억제(Vibration Suppression)는 동적 하중 보상의 대표적인 응용 분야이다.

구조물은 동적 힘을 받을 때 진동한다.

진동은 위치 정밀도(Position Accuracy)를 떨어뜨리고 센서 품질(Sensor Quality)을 저하시킨다.

또한 피로 손상(Fatigue Damage)을 증가시킨다.

이를 해결하기 위해 능동 감쇠(Active Damping), 적응형 필터링(Adaptive Filtering), 공진 회피(Resonance Avoidance) 기술이 사용된다.

센서 기술(Sensor Technology)은 현대 동적 보상의 핵심이다.

IMU(Inertial Measurement Unit)는 가속도와 각속도를 측정한다.

Force-Torque Sensor는 접촉력을 측정한다.

Encoder는 위치와 속도를 측정한다.

Wheel Encoder는 차량 운동 상태를 측정한다.

GNSS RTK는 절대 위치 정보를 제공한다.

LiDAR와 Vision System은 주변 환경 정보를 제공한다.

상태 추정(State Estimation)은 여러 센서 데이터를 융합하는 과정이다.

칼만 필터(Kalman Filter), 확장 칼만 필터(Extended Kalman Filter), 언센티드 칼만 필터(Unscented Kalman Filter), 파티클 필터(Particle Filter)가 널리 사용된다.

이들은 위치, 속도, 가속도, 힘, 외란을 추정하여 보상 시스템에 제공한다.

피드포워드 제어(Feedforward Control)는 동적 보상에서 매우 중요하다.

오차가 발생한 후 수정하는 것이 아니라, 미리 필요한 힘과 토크를 계산하여 적용한다.

이를 통해 빠른 동작에서도 높은 추종 성능을 얻을 수 있다.

피드백 제어(Feedback Control)는 여전히 필수적이다.

어떠한 모델도 완벽하지 않기 때문에 예측하지 못한 외란이 발생한다.

피드백 제어는 이러한 잔여 오차(Residual Error)를 제거한다.

모델 기반 제어(Model-Based Control)는 동역학 모델을 직접 사용한다.

대표적으로 계산 토크 제어(Computed Torque Control)가 있다.

이는 로봇 동역학을 실시간 계산하여 필요한 토크를 생성하는 방식이다.

적응 제어(Adaptive Control)는 운용 중 모델 파라미터를 지속적으로 업데이트한다.

페이로드 변화, 부품 마모, 온도 변화가 발생하더라도 높은 성능을 유지할 수 있다.

최근에는 AI 기반 동적 보상(AI-Based Dynamic Compensation)이 빠르게 발전하고 있다.

머신러닝(Machine Learning)과 신경망(Neural Network)은 기존 물리 모델이 설명하기 어려운 복잡한 동적 현상을 학습할 수 있다.

강화학습(Reinforcement Learning)은 최적의 보상 전략을 스스로 학습할 수 있다.

예측 제어(Predictive Control)는 미래 상태를 예측하여 제어한다.

모델 예측 제어(Model Predictive Control, MPC)는 모바일 매니퓰레이터와 자율주행 플랫폼에서 매우 유망한 기술로 평가받고 있다.

동적 하중 보상은 에너지 효율(Energy Efficiency)에도 큰 영향을 준다.

보상이 부족하면 액추에이터가 불필요하게 많은 힘을 사용하게 된다.

정확한 보상은 전력 소비를 줄이고 배터리 수명을 연장한다.

특히 배터리 기반 AMR에서는 매우 중요한 효과를 제공한다.

안전성(Safety) 역시 동적 보상과 밀접하게 관련되어 있다.

과도한 동적 하중은 전복(Rollover), 구조 손상(Structural Damage), 페이로드 낙하(Payload Drop), 충돌(Collision)을 유발할 수 있다.

따라서 동적 보상 시스템은 항상 안전 한계(Safety Limit)를 감시해야 한다.

대형 페이로드 처리(Heavy Payload Handling)는 가장 어려운 응용 분야 중 하나이다.

무거운 하중은 관성을 증가시키고 무게 중심을 이동시키며 구조 응력을 증가시킨다.

동적 하중 보상은 이러한 조건에서도 정밀도와 안정성을 유지할 수 있게 해준다.

디지털 트윈(Digital Twin)은 동적 보상 개발을 크게 향상시키고 있다.

가상 환경에서 동역학, 구조 거동, 센서 응답, 제어 알고리즘을 시뮬레이션하여 최적의 보상 전략을 찾을 수 있다.

미래의 동적 하중 보상 기술은 물리 기반 모델(Physics-Based Model), AI 예측(AI Prediction), 적응 제어(Adaptive Control), 디지털 트윈(Digital Twin), 실시간 센서 융합(Real-Time Sensor Fusion)을 통합한 지능형 제어 구조(Intelligent Control Architecture)로 발전할 것이다.

자율 물류(Autonomous Logistics), 스마트 제조(Intelligent Manufacturing), 모바일 매니퓰레이션(Mobile Manipulation), 자율 검사(Autonomous Inspection), 서비스 로봇(Service Robot), 피지컬 AI 시대가 발전할수록 동적 하중 보상은 더욱 중요한 핵심 기술이 될 것이다.

결국 동적 하중 보상은 로봇이 이론적인 운동 모델(Theoretical Motion Model)을 실제 환경(Real World)에서 안정적으로 구현하도록 만드는 핵심 연결 기술(Core Bridging Technology)이다. 이는 더 높은 정밀도(Higher Accuracy), 더 우수한 안정성(Greater Stability), 더 높은 에너지 효율(Better Energy Efficiency), 더 강한 안전성(Enhanced Safety), 그리고 더 뛰어난 임무 수행 능력(Superior Mission Performance)을 가능하게 하는 차세대 지능형 로봇 시스템의 필수 기반 기술이라고 할 수 있다.

## 6.4 Whole Body Control Electrical

![](images/image4.png){width="7.268055555555556in" height="7.268055555555556in"}

# 06_04 전신 제어 전기 아키텍처(Whole Body Control Electrical)

전신 제어 전기 아키텍처(Whole Body Control Electrical)는 로봇 플랫폼 내부의 모든 전기·전자 시스템(Electrical and Electronic System)을 하나의 통합된 동적 시스템(Integrated Dynamic System)으로 제어하기 위한 핵심 아키텍처이다. 현대의 자율이동로봇(Autonomous Mobile Robot, AMR), 모바일 매니퓰레이터(Mobile Manipulator), 산업용 서비스 로봇(Industrial Service Robot), 휴머노이드 로봇(Humanoid Robot), 실외 자율주행 플랫폼(Outdoor Autonomous Platform), 물류 로봇(Logistics Robot), 그리고 피지컬 AI(Physical AI) 시스템에서는 더 이상 각 장치가 독립적으로 동작해서는 안 된다.

과거에는 주행 시스템(Drive System), 조향 시스템(Steering System), 로봇 암(Robot Arm), 센서(Sensor), 제어기(Controller)가 각각 독립적으로 설계되었다. 이러한 구조는 고정형 산업용 로봇(Fixed Industrial Robot)에서는 충분히 효과적이었다. 그러나 이동(Mobility), 조작(Manipulation), 인지(Perception), 자율성(Autonomy), 협업(Collaboration)이 요구되는 현대 로봇에서는 하나의 서브시스템(Sub-System)에서 발생한 변화가 다른 모든 시스템에 영향을 미친다.

예를 들어 로봇 암이 무거운 물체를 들어 올리면 차량의 안정성(Stability)이 변화한다. 차량이 가속하면 매니퓰레이터의 위치 정밀도(Position Accuracy)가 영향을 받는다. 센서 위치는 인식 성능(Perception Performance)에 영향을 주며, 전력 소비(Power Consumption)는 전체 임무 수행 능력(Mission Capability)을 변화시킨다.

전신 제어는 이러한 문제를 해결하기 위해 등장하였다.

전신 제어 전기 아키텍처는 전력(Power), 통신(Communication), 센서(Sensor), 액추에이터(Actuator), 컴퓨팅(Computing), 안전(Safety)을 하나의 통합 제어 구조(Unified Control Architecture)로 결합한다.

생물학적으로 보면 전신 제어 전기 아키텍처는 로봇의 신경계(Nervous System)에 해당한다.

배터리는 심장(Heart) 역할을 수행한다.

전력 시스템은 혈관(Vascular System)에 해당한다.

센서는 감각기관(Sensory Organ)에 해당한다.

액추에이터는 근육(Muscle)에 해당한다.

통신 네트워크는 신경망(Neural Network)에 해당한다.

AI와 제어기는 두뇌(Brain)의 역할을 수행한다.

전신 제어 전기 아키텍처는 이 모든 요소를 통합하여 로봇 전체가 하나의 생명체처럼 움직이도록 만든다.

전신 제어의 가장 기본적인 요소는 전력 아키텍처(Power Architecture)이다.

모든 시스템은 전기 에너지(Electrical Energy)에 의존하며, 전력 공급 능력은 전체 제어 성능을 결정한다.

전원은 일반적으로 다음과 같은 형태로 구성된다.

리튬인산철 배터리(Lithium Iron Phosphate, LFP)

리튬 니켈 망간 코발트 배터리(Lithium Nickel Manganese Cobalt, NMC)

연료전지(Fuel Cell)

하이브리드 전원(Hybrid Power System)

산업용 전원 공급 장치(Industrial Power Supply)

사용자가 개발 중인 실외 AMR 플랫폼에서는 48V LFP 배터리가 가장 적합한 구조 중 하나이다.

주 전력 버스(Main Power Bus)는 전체 시스템에 전력을 공급한다.

일반적으로 다음과 같은 전압 체계가 사용된다.

24V 시스템

48V 시스템

72V 시스템

96V 이상 고전압 시스템

실외 AMR, 물류 로봇, 중대형 모바일 매니퓰레이터에서는 48V가 가장 많이 사용된다.

전력 분배 장치(Power Distribution Unit, PDU)는 전체 전력 흐름을 관리한다.

PDU는 전류(Current), 전압(Voltage), 온도(Temperature), 소비 전력(Power Consumption)을 모니터링하며 다음 기능을 수행한다.

전력 분배(Power Distribution)

과전류 보호(Overcurrent Protection)

단락 보호(Short Circuit Protection)

전압 안정화(Voltage Regulation)

장치 격리(Device Isolation)

전신 제어는 PDU에서 수집된 정보를 이용하여 전체 시스템의 상태를 판단한다.

액추에이터 네트워크(Actuator Network)는 로봇의 근육 시스템에 해당한다.

주행 모터(Drive Motor)

조향 액추에이터(Steering Actuator)

매니퓰레이터 조인트(Manipulator Joint)

그리퍼(Gripper)

리니어 액추에이터(Linear Actuator)

서스펜션 액추에이터(Suspension Actuator)

등이 포함된다.

전신 제어는 이들을 각각 제어하는 것이 아니라 하나의 통합 시스템으로 제어한다.

서보 드라이브(Servo Drive)는 현대 전신 제어의 핵심 구성 요소이다.

서보 드라이브 내부에는 다음 기능이 포함된다.

전류 루프(Current Loop)

속도 루프(Velocity Loop)

위치 루프(Position Loop)

토크 추정(Torque Estimation)

진단 기능(Diagnostics)

통신 인터페이스(Communication Interface)

전신 제어기는 이러한 정보를 수집하여 전체 로봇 상태를 계산한다.

통신 네트워크(Communication Network)는 전신 제어의 신경망 역할을 수행한다.

현대 로봇에서는 수십 개에서 수백 개의 장치가 연결된다.

대표적인 프로토콜은 다음과 같다.

EtherCAT은 특히 전신 제어에 적합하다.

결정론적 실시간 통신(Deterministic Real-Time Communication)

분산 클록(Distributed Clock)

마이크로초 수준 동기화(Microsecond-Level Synchronization)

고속 순환 데이터 교환(High-Speed Cyclic Data Exchange)

기능을 제공하기 때문이다.

CAN은 배터리 관리(Battery Management), 진단(Diagnostics), 환경 센서(Environmental Sensor), 전력 관리(Power Management)에 적합하다.

실제로 사용자가 개발 중인 실외 AMR 플랫폼에서도 EtherCAT과 CAN FD의 혼합 구조가 매우 적절하다.

센서 시스템(Sensor System)은 전신 제어의 감각기관 역할을 수행한다.

전신 제어는 로봇의 상태(State)와 환경(Environment)을 정확하게 알아야 한다.

대표적인 센서는 다음과 같다.

안전 스캐너(Safety Scanner)

센서 융합(Sensor Fusion)은 전신 제어의 핵심 기술이다.

단일 센서만으로는 전체 상태를 파악할 수 없다.

따라서 여러 센서 데이터를 결합하여 하나의 통합 상태 정보를 생성한다.

주요 알고리즘은 다음과 같다.

칼만 필터(Kalman Filter)

확장 칼만 필터(Extended Kalman Filter)

언센티드 칼만 필터(Unscented Kalman Filter)

파티클 필터(Particle Filter)

AI 기반 추정(AI-Based Estimation)

상태 추정(State Estimation)은 전신 제어의 기반이다.

제어기는 다음을 지속적으로 추정한다.

위치(Position)

자세(Orientation)

속도(Velocity)

가속도(Acceleration)

조인트 상태(Joint State)

페이로드 특성(Payload Characteristics)

휠 슬립(Wheel Slip)

배터리 상태(Battery State)

열 상태(Thermal State)

환경 제약(Environmental Constraint)

컴퓨팅 아키텍처(Computing Architecture)는 최근 더욱 중요해지고 있다.

전신 제어 시스템은 일반적으로 다계층 구조(Multi-Layer Architecture)를 가진다.

저수준 제어기(Low-Level Controller)는 모터를 제어한다.

중간 제어기(Mid-Level Controller)는 서브시스템을 관리한다.

고성능 엣지 컴퓨터(High-Performance Edge Computer)는 인식, 계획, AI 추론을 수행한다.

클라우드 시스템(Cloud System)은 플릿 관리(Fleet Management)와 데이터 분석(Data Analytics)을 수행한다.

분산 컴퓨팅(Distributed Computing)은 확장성과 안정성을 향상시킨다.

모든 기능을 하나의 CPU에서 수행하는 대신 여러 장치에 분산시킨다.

이는 사용자가 설계 중인 Orin NX + Edge PC + RTX GPU 구조와 매우 유사하다.

전신 제어의 가장 중요한 목적 중 하나는 운동 협조(Motion Coordination)이다.

기존 시스템은 차량 제어(Vehicle Control)와 로봇 암 제어(Manipulator Control)를 분리하였다.

전신 제어는 전체 로봇을 하나의 운동학 시스템(Kinematic System)과 동역학 시스템(Dynamic System)으로 본다.

예를 들어 모바일 매니퓰레이터가 무거운 물체를 들어 올릴 때 전신 제어기는 다음을 동시에 수행한다.

휠 토크(Wheel Torque) 조정

서스펜션 조정(Suspension Adjustment)

암 궤적 수정(Arm Trajectory Adjustment)

차량 자세 제어(Vehicle Posture Control)

이를 통해 전복(Rollover)을 방지하고 안정성을 유지한다.

동적 하중 보상(Dynamic Load Compensation)은 전신 제어와 밀접하게 연결된다.

매니퓰레이터가 움직이면 차량의 무게 중심(Center of Gravity)이 변한다.

차량이 가속하면 매니퓰레이터에 관성 하중(Inertial Load)이 발생한다.

전신 제어기는 이를 예측하고 보상한다.

에너지 관리(Energy Management)는 또 다른 핵심 요소이다.

전신 제어기는 다음 정보를 지속적으로 모니터링한다.

소비 전력(Power Consumption)

온도(Thermal Condition)

임무 우선순위(Mission Priority)

이를 기반으로 전력을 배분한다.

열 관리(Thermal Management)도 중요하다.

배터리

모터

인버터(Inverter)

통신 장치

는 모두 열을 발생시킨다.

전신 제어기는 온도 정보를 활용하여 성능과 안전성을 유지한다.

안전 시스템(Safety System)은 전신 제어의 필수 구성 요소이다.

비상 정지(Emergency Stop)

안전 PLC(Safety PLC)

충돌 회피(Collision Avoidance)

안전 라이다(Safety LiDAR)

속도 제한(Speed Limitation)

기능이 통합된다.

안전 기능은 독립적으로 존재하는 것이 아니라 전신 제어와 연동된다.

AI는 전신 제어를 더욱 발전시키고 있다.

머신러닝(Machine Learning)은 이상 상태(Anomaly Detection)를 탐지한다.

강화학습(Reinforcement Learning)은 최적 제어 정책(Control Policy)을 학습한다.

예측 모델(Predictive Model)은 미래 상태를 예측한다.

모델 예측 제어(Model Predictive Control, MPC)는 전신 제어에서 매우 유망한 기술로 평가받고 있다.

디지털 트윈(Digital Twin)은 전신 제어 개발에 매우 중요한 도구가 되고 있다.

가상 로봇(Virtual Robot)은 실제 로봇의 동역학, 전기 특성, 통신 상태, 열 거동을 시뮬레이션할 수 있다.

이를 통해 설계를 최적화하고 유지보수를 예측할 수 있다.

향후 전신 제어 전기 아키텍처는 다음 방향으로 발전할 것으로 예상된다.

AI 기반 제어(AI-Based Control)

실시간 디지털 트윈(Real-Time Digital Twin)

분산 지능(Distributed Intelligence)

Edge-Cloud 협업(Edge-Cloud Cooperation)

적응 제어(Adaptive Control)

에너지 최적화(Energy Optimization)

자가 진단(Self-Diagnostics)

자가 복구(Self-Recovery)

피지컬 AI 시대에는 로봇이 자신의 전기 상태(Electrical State), 기계 상태(Mechanical State), 열 상태(Thermal State), 통신 상태(Communication State)를 스스로 이해하고 최적화하는 방향으로 발전하게 된다.

결국 전신 제어 전기 아키텍처는 모터(Motor), 센서(Sensor), 배터리(Battery), 컴퓨터(Computer), 네트워크(Network), AI를 하나의 지능형 생명체(Intelligent Organism)처럼 동작하게 만드는 핵심 기술(Core Enabling Technology)이다. 이는 차세대 AMR, 모바일 매니퓰레이터, 실외 자율주행 플랫폼, 휴머노이드 로봇, 그리고 피지컬 AI 시스템의 가장 중요한 기반 아키텍처 중 하나가 될 것이다.

## 6.5 Mobile Manipulator Safety

![](images/image5.png){width="7.268055555555556in" height="7.268055555555556in"}

# 06_05 모바일 매니퓰레이터 안전(Mobile Manipulator Safety)

모바일 매니퓰레이터 안전(Mobile Manipulator Safety)은 현대 로봇 공학(Robotics)에서 가장 중요한 분야 중 하나이다. 이는 자율이동로봇(Autonomous Mobile Robot, AMR)의 안전 문제와 로봇 매니퓰레이터(Robot Manipulator)의 안전 문제를 하나의 시스템 안에서 동시에 해결해야 하기 때문이다.

모바일 매니퓰레이터는 단순한 산업용 로봇과 다르다. 이동(Mobility)과 조작(Manipulation)을 동시에 수행할 수 있으며, 작업 공간 전체를 자유롭게 이동하면서 다양한 작업을 수행한다. 따라서 주행 시스템(Drive System), 매니퓰레이터 시스템(Manipulator System), 인지 시스템(Perception System), 제어 시스템(Control System), 통신 시스템(Communication System), 전력 시스템(Power System), 인공지능(AI), 그리고 작업자(Human Operator) 사이의 상호작용을 모두 고려해야 한다.

전통적인 산업용 로봇은 일반적으로 안전 펜스(Safety Fence) 내부에서 동작하였다. 사람은 작업 중인 로봇에 접근할 수 없었으며, 물리적인 분리(Physical Separation)를 통해 안전을 확보하였다. 그러나 모바일 매니퓰레이터는 창고(Warehouse), 공장(Factory), 병원(Hospital), 공항(Airport), 물류센터(Logistics Center), 건설 현장(Construction Site), 농업 환경(Agricultural Environment), 공공시설(Public Facility)과 같이 사람이 존재하는 공간에서 함께 동작한다.

이러한 환경에서는 물리적 분리만으로 안전을 확보할 수 없다. 따라서 안전 기능이 로봇 내부에 직접 통합되어야 한다.

모바일 매니퓰레이터 안전의 궁극적인 목표는 사람의 부상(Injury), 장비 손상(Equipment Damage), 페이로드 손실(Payload Loss), 환경 피해(Environmental Damage), 그리고 시스템 고장(System Failure)을 방지하면서도 생산성과 효율성을 유지하는 것이다.

모바일 매니퓰레이터는 두 개의 주요 운동 시스템(Motion System)을 동시에 가진다.

첫 번째는 모바일 베이스(Mobile Base)이다.

두 번째는 로봇 암(Robot Arm)이다.

모바일 베이스는 전진, 후진, 회전, 조향을 수행하며, 매니퓰레이터는 다축 운동(Multi-Axis Motion)을 수행한다.

이 두 시스템은 지속적으로 상호작용한다. 따라서 차량 안전(Vehicle Safety)만 고려하거나 매니퓰레이터 안전(Manipulator Safety)만 고려해서는 충분하지 않다.

전체 시스템을 하나의 통합체(Unified System)로 보는 전신 안전(Whole Body Safety) 접근이 필요하다.

안전 설계의 출발점은 위험성 평가(Risk Assessment)이다.

엔지니어는 다음과 같은 위험 요소를 식별한다.

충돌(Collision)

협착(Crushing)

끼임(Pinching)

충격(Impact)

낙하(Falling Payload)

전기적 고장(Electrical Fault)

소프트웨어 오류(Software Failure)

통신 장애(Communication Failure)

센서 오작동(Sensor Malfunction)

예상치 못한 인간 행동(Unpredictable Human Behavior)

위험성 평가는 정상 운용(Normal Operation)뿐만 아니라 유지보수(Maintenance), 수동 조작(Manual Operation), 충전(Charging), 비상 복구(Emergency Recovery), 소프트웨어 업데이트(Software Update) 상황까지 포함해야 한다.

기능 안전(Functional Safety)은 모바일 매니퓰레이터 안전의 핵심이다.

기능 안전은 고장이 발생하더라도 시스템이 안전한 상태(Safe State)를 유지하도록 보장하는 기술이다.

이를 위해 다음과 같은 요소가 사용된다.

중복성(Redundancy)

고장 진단(Fault Detection)

자가 진단(Self-Diagnostics)

안전 상태 전환(Safe-State Transition)

페일 세이프(Fail-Safe) 설계

안전 기능은 여러 계층(Layer)으로 구성된다.

비상 정지(Emergency Stop)는 가장 기본적인 안전 기능이다.

위험 상황이 발생하면 모든 동작을 즉시 정지시킨다.

STO(Safe Torque Off)는 모터에 공급되는 토크를 제거하여 안전하게 정지시킨다.

안전 제어기(Safety Controller)는 전체 안전 기능을 감시하고 조정한다.

충돌 회피(Collision Avoidance)는 모바일 매니퓰레이터에서 가장 중요한 기능 중 하나이다.

로봇은 사람, 차량, 장애물, 설비를 지속적으로 감지해야 한다.

이를 위해 다음과 같은 센서가 사용된다.

센서 융합(Sensor Fusion)은 여러 센서의 정보를 결합하여 보다 정확한 환경 인식(Environmental Awareness)을 수행한다.

최근에는 AI 기반 인식(AI-Based Perception)이 적용되고 있다.

AI는 사람(Human), 차량(Vehicle), 장애물(Obstacle)을 구분할 수 있으며 사람의 움직임과 의도(Intent)까지 예측할 수 있다.

안전 구역(Safety Zone)은 매우 널리 사용되는 개념이다.

외곽 구역(Outer Zone)은 감속(Speed Reduction)을 유도한다.

중간 구역(Middle Zone)은 더욱 엄격한 속도 제한을 적용한다.

내부 구역(Inner Zone)은 비상 정지를 수행한다.

동적 안전 구역(Dynamic Safety Zone)은 로봇 속도, 적재 중량, 매니퓰레이터 상태에 따라 크기가 자동으로 변한다.

속도 및 거리 감시(Speed and Separation Monitoring)는 협동 로봇(Collaborative Robot) 분야에서 매우 중요한 기술이다.

로봇은 사람과의 거리를 지속적으로 계산한다.

거리가 가까워질수록 자동으로 속도를 낮춘다.

이 방식은 생산성과 안전성을 동시에 확보할 수 있게 해준다.

매니퓰레이터 안전은 차량 안전보다 더 복잡한 경우가 많다.

다축 로봇 암은 협착점(Pinch Point), 압착 위험(Crushing Hazard), 충돌 위험(Impact Hazard), 감김 위험(Entanglement Hazard)을 만들 수 있다.

따라서 모든 조인트(Joint)의 위치(Position), 속도(Velocity), 가속도(Acceleration), 힘(Force), 토크(Torque)를 지속적으로 감시해야 한다.

힘 제한 제어(Force-Limited Control)는 사람과 협업하는 환경에서 중요하다.

토크 센서(Torque Sensor), 힘 센서(Force Sensor), 컴플라이언스 제어(Compliance Control)를 이용하여 접촉력이 일정 수준 이상 증가하면 자동으로 속도를 줄이거나 정지한다.

페이로드 안전(Payload Safety)도 매우 중요하다.

모바일 매니퓰레이터는 물체를 이동하고 들어 올리며 조작한다.

만약 물체가 떨어지면 심각한 사고가 발생할 수 있다.

따라서 다음 장치의 신뢰성이 중요하다.

그리퍼(Gripper)

진공 그리퍼(Vacuum Gripper)

자동 공구 교환기(Automatic Tool Changer, ATC)

툴 인터페이스(Tool Interface)

무게 중심 관리(Center of Gravity Management)는 특히 대형 AMR에서 중요하다.

매니퓰레이터의 움직임과 페이로드 변화는 무게 중심을 지속적으로 이동시킨다.

무게 중심이 지나치게 이동하면 다음 문제가 발생할 수 있다.

전복(Rollover)

제동 거리 증가(Braking Distance Increase)

조향 성능 저하(Steering Performance Reduction)

바퀴 미끄러짐(Wheel Slip)

따라서 안정성 모니터링(Stability Monitoring)이 필요하다.

실외 AMR에서는 전복 방지(Rollover Prevention)가 더욱 중요하다.

경사면(Slope)

비포장 도로(Rough Terrain)

급회전(Sharp Turning)

급가속(Rapid Acceleration)

높은 적재물(Elevated Payload)

은 모두 전복 위험을 증가시킨다.

전신 제어(Whole Body Control)는 무게 중심과 지지 다각형(Support Polygon)을 실시간 계산하여 위험 상황을 예방한다.

전기 안전(Electrical Safety)은 모든 안전 설계의 기본이다.

모바일 매니퓰레이터는 대용량 배터리(Battery), 인버터(Inverter), 모터 드라이브(Motor Drive), GPU, 엣지 컴퓨터(Edge Computer)를 포함한다.

주요 위험 요소는 다음과 같다.

감전(Electrical Shock)

단락(Short Circuit)

아크 결함(Arc Fault)

과열(Overheating)

배터리 열폭주(Thermal Runaway)

전자파 간섭(Electromagnetic Interference)

배터리 관리 시스템(Battery Management System, BMS)은 전압, 전류, 온도, 충전 상태(State of Charge), 건강 상태(State of Health)를 지속적으로 모니터링한다.

통신 안전(Communication Safety) 역시 중요하다.

모바일 매니퓰레이터는 다음 장치 간의 통신에 의존한다.

센서

제어기

액추에이터

안전 시스템

클라우드 서비스

통신 장애가 발생하면 안전 기능이 영향을 받을 수 있다.

따라서 이중화 통신(Redundant Communication), Heartbeat Monitoring, Timeout Detection이 적용된다.

사이버보안(Cybersecurity)은 최근 안전의 중요한 일부가 되었다.

해킹(Hacking), 위조 명령(Spoofing), 악성 코드(Malware), 무단 접근(Unauthorized Access)은 실제 물리적 사고를 유발할 수 있다.

따라서 다음 기능이 필요하다.

인증(Authentication)

암호화(Encryption)

접근 제어(Access Control)

침입 탐지(Intrusion Detection)

환경 안전(Environmental Safety)은 적용 분야에 따라 달라진다.

실내 환경은 사람, 지게차(Forklift), 선반(Rack), 협소 공간(Confined Space)이 주요 위험 요소이다.

실외 환경은 비(Rain), 눈(Snow), 먼지(Dust), 온도 변화(Temperature Variation), 조도 변화(Lighting Variation), 험지(Terrain)가 주요 위험 요소이다.

인간-기계 상호작용(Human-Machine Interaction)은 가장 어려운 문제 중 하나이다.

사람은 예측 불가능한 행동을 할 수 있다.

따라서 로봇은 자신의 상태와 의도를 명확하게 전달해야 한다.

이를 위해 다음 기능이 사용된다.

상태 표시등(Status Light)

경고음(Audio Warning)

디스플레이(Display)

AI는 안전 기능을 더욱 발전시키고 있다.

머신러닝(Machine Learning)은 이상 행동(Anomaly Detection)을 감지한다.

AI는 사람의 행동(Human Behavior)을 예측할 수 있다.

환경 변화(Environmental Change)를 이해할 수 있다.

그러나 안전 핵심 기능(Safety-Critical Function)은 여전히 결정론적 제어(Deterministic Control) 아래에서 운영되는 것이 일반적이다.

전신 안전 제어(Whole Body Safety Control)는 모바일 베이스와 매니퓰레이터를 하나의 시스템으로 본다.

이 방식은 다음 기능을 통합한다.

모션 계획(Motion Planning)

충돌 회피(Collision Avoidance)

힘 제어(Force Control)

안정성 제어(Stability Control)

에너지 관리(Energy Management)

환경 인식(Environmental Awareness)

동적 하중 보상(Dynamic Load Compensation)은 안전성을 향상시킨다.

관성력(Inertial Force), 진동(Vibration), 외란(Disturbance), 페이로드 변화(Payload Variation)를 보상함으로써 안정성과 제어 정확도를 향상시킨다.

안전 검증(Safety Validation)은 실제 배포 이전에 반드시 수행되어야 한다.

시뮬레이션(Simulation)

디지털 트윈(Digital Twin)

현장 시험(Field Trial)

고장 주입 시험(Fault Injection Test)

을 통해 안전성을 검증한다.

예측 안전(Predictive Safety)은 차세대 안전 기술이다.

위험이 발생한 후 대응하는 것이 아니라, 위험을 사전에 예측하고 회피한다.

AI와 디지털 트윈을 활용하면 미래 위험을 미리 계산할 수 있다.

다수의 모바일 매니퓰레이터가 동시에 동작하는 플릿(Fleet) 환경에서는 플릿 안전(Fleet Safety)이 중요해진다.

플릿 관리 시스템(Fleet Management System)은 교통 흐름(Traffic Flow), 충전 스케줄(Charging Schedule), 작업 할당(Task Allocation)을 조정하여 전체 시스템의 안전성을 유지한다.

미래의 모바일 매니퓰레이터 안전 기술은 고급 센서(Advanced Sensor), AI 기반 위험 분석(AI-Based Risk Analysis), 디지털 트윈(Digital Twin), 예측 분석(Predictive Analytics), 분산 안전 지능(Distributed Safety Intelligence), 적응형 제어(Adaptive Control)를 통합한 형태로 발전할 것이다.

자율 물류(Autonomous Logistics), 스마트 제조(Intelligent Manufacturing), 의료 로봇(Medical Robotics), 건설 로봇(Construction Robotics), 농업 로봇(Agricultural Robotics), 사회 인프라 점검(Infrastructure Inspection), 피지컬 AI 분야가 성장할수록 모바일 매니퓰레이터 안전은 더욱 중요한 핵심 기술이 될 것이다.

결국 모바일 매니퓰레이터 안전은 기계 안전(Mechanical Safety), 전기 안전(Electrical Safety), 기능 안전(Functional Safety), 사이버보안(Cybersecurity), 환경 인식(Environmental Awareness), 인공지능(AI), 전신 제어(Whole Body Control)를 하나의 통합 프레임워크(Integrated Framework)로 결합하는 기술이다. 이는 사람(Human), 자산(Asset), 환경(Environment), 그리고 임무(Mission)를 동시에 보호하면서 로봇이 실제 환경에서 신뢰성 있게 운영될 수 있도록 만드는 차세대 지능형 로봇 시스템의 핵심 기반 기술이라고 할 수 있다.

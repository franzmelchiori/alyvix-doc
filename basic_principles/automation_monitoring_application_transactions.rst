*****************************************************
Automation and monitoring of application transactions
*****************************************************


Critical user transactions
==========================

An **application transaction** is the gap between an application interface interaction and its result visualization. Several factors affect the time that an application takes to fill each gap. They mostly have to deal with software optimization, hardware resources and telecommunications channels.

A desktop application that is fetching a database takes time to **retrieve and visualize data**. The client software could be poorly optimized, the database could be available from few and slow virtual machines and the network traffic could be congested at that time: in such a scenario end users suffer **latencies** or even **downtimes**.

Ensuring the **performances of business critical transactions**, from the **prospective of end user perception**, is an important asset for organizations that provide IT services. Monitoring those performances is the first step to improve the **quality of service**.


Visual Synthetic Monitoring
===========================

**Visual** means that Alyvix looks at an application **graphical user interface** (GUI) exactly as you do: if you can see something on your screen Alyvix can do that too and vice versa. **Synthetic** means that Alyvix synthetizes **human users** behaving like them: if you can interact with an application GUI, no matter what the interaction mode is (mouse clicks, keystrokes, etc.), Alyvix can do that too. **Monitoring** means that an Alyvix system tracks performances of application transactions: you can analyze time series of your **business critical transactions**, where latency spikes and downtime gaps are evident.

The idea is to monitor certain **user interaction flows** where business critical transactions take place in desktop applications or web services. Those flows can be replicated as sequences of transactions: Alyvix provides tools to define every transaction and to serialize transactions within executable **test cases**. As a result of executing test cases with Alyvix it is possible for every listed transaction to check its **availability** (i.e. it does not fail) and to measure its **responsiveness**, so the amount of milliseconds that the application takes from the end of the last interaction to the appearance of the defined graphic elements.

Executing the same Alyvix test case continuously (e.g. hourly) and from different locations (having several cloned machines sending performance data from several hotspots) it is possible to assess the **quality of service** of the given application. Alyvix system shows and notifies when (date and time), where (machine IP) and why (application screenshot with graphic elements to detect) that the quality of service decreased or lacked at all. That means doing **visual synthetic monitoring**.


Alyvix solution
===============

Alyvix is a solution for monitoring **critical user transactions** of any application from the point of view of the **end user visual perception** as Alyvix is a software system for visual synthetic monitoring.

Alyvix automates any application, interacting with any GUI exactly as a human would do. Alyvix measures how long application transactions take and visualizes their performances in monitoring systems. Alyvix reports HTML pages containing the details of each test case step.

Alyvix certifies that users are able to successfully complete a certain application task, in a given moment and location, with a certain quality of service. IT operation teams can **modulate infrastructure resources**. Clients of IT companies can **check the SLA with providers**.

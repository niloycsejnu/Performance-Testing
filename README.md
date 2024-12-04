# Performance Test Using JMeter

This repository contains JMeter performance test scenarios for two projects: **Booking API** and **Dmoney API**. The goal is to conduct load and stress testing to evaluate the system's performance under specified conditions and ensure its reliability. 

---

## Task 1: Booking API Performance Testing

### Scenario
120,000 users over a 12-hour period:
1. Log in.
2. Create a booking.
3. Search for the booking.

---

### Steps to Perform:

#### **Step 1: Create a JMeter Collection**
- File: `booking.jmx`
- Tasks:
  1. Login
  2. Create Booking
  3. Search Booking

#### **Step 2: Load Test**
- Use a **Gaussian Random Timer**:
  - Deviation: `2000ms`
  - Constant Delay: `500ms`
- Perform load tests in 3 phases:
  1. **5 minutes** load
  2. **10 minutes** load
  3. **20 minutes** load

- **Objective:** Measure throughput and ensure the server can handle the load.
- **Output:** Load test report.

#### **Step 3: Stress Test**
- Gradually increase the number of users for booking creation until the server breaks down.
- **Objective:** Identify the bottleneck throughput.
- **Output:** Stress test report.

---

### Outputs:
**The Load & Stress Test Reports are here:** [Click Here to see the Report](https://docs.google.com/spreadsheets/d/1Qe05DvqD-Lm7qvrr7jMmFAW35OGkguFX/edit?usp=sharing&ouid=105207321304680998857&rtpof=true&sd=true) 

# The screenshot of Load Test for booking.jmx:

![ss1](https://github.com/user-attachments/assets/89e06818-efd7-48c3-a98b-3ec70c433bf9
)
---
# The screenshot of Stress Test for booking.jmx:
![ss2](https://github.com/user-attachments/assets/65c0be55-a4b3-4af8-b01f-59472c932c2b
)
-
# The screenshot of Load Test Report for booking.jmx:

![ss3](https://github.com/user-attachments/assets/b9918dcf-d7ec-447d-88b3-9be2be8e7bf7
)
---
# The screenshot of Stress Test Report for booking.jmx:

![ss4](https://github.com/user-attachments/assets/fabc80fe-fd67-4a0d-9d3a-2672816483e6
)
---


## Task 2: Dmoney API Performance Testing

### Scenario
1. **Deposits:** 5 agents perform deposits for 10 customers.
2. **Send Money:** 5 customers send money to another 10 customers.
3. **Payments:** 5 customers make payments to 2 merchants.

---

### Steps to Perform:

#### **Step 1: Create a JMeter Collection**
- File: `dmoney.jmx`
- Setup:
  - Use CSV files to define accounts for agents, customers, and merchants:
    - `deposit.csv`
    - `sendMoney.csv`
    - `payment.csv`
  - Use the **Random Variable Controller** for dynamic amounts.
  - Ensure small transaction amounts to avoid balance depletion.
  - Use assertions to verify the success of all transactions.

#### **Step 2: Thread Configuration**
- Create 3 threads for each transaction type.
- Ramp-up time: `120 seconds`.

---

### Outputs:
# The screenshots of the request summary and statistics from the generated HTML report for DMoney Jmeter Collection Test 

![ss5](https://github.com/user-attachments/assets/64351159-4b52-4a0f-adfd-d7753a95fb04
)
---

![ss6](https://github.com/user-attachments/assets/22b91f06-b14e-4cee-aaa7-4945e94c6b2c
)
-

---

## How to Run the Tests

### Installation
**Clone the Repository in Apache Jmeter**  
- Open your terminal and run:  
   `git clone https://github.com/niloycsejnu/Performance-Testing.git`
  
**Execute the following steps using CLI:**
- For Booking APIs JMeter Collection
 `jmeter -n -t '.\booking.jmx' -l '.\booking.jtl' -e -o Reports`
- For Dmoney APIs JMeter Collection
 `jmeter -n -t '.\dmoney.jmx' -l '.\dmoney.jtl' -e -o Reports`

## Contact

For any questions or issues, feel free to open an issue in the repository or contact me via [GitHub](https://github.com/niloycsejnu) or [Email](niloydatta0011@gmail.com)

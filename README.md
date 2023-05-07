# Test analytic for VK intern programm

## Project navigation: 

1. [Data cleaning ](#1)
2. [Analysis registered users](#2) 
3. [Analysis active and inactive users](#3)
4. [Creation of correlation matrix](#4)
5. [Analysis device activity](#5)
6. [Analysis gvm statistics](#6)
7. [Check influence "is_msk" column on gvm activity](#7)

## Realized steps

### 1. Data cleaning (drop usless columns, Nan values, rename columns, convert types) <a name="1"></a>
### 2. Analysis registered users <a name="2"></a>
  
  ![1 vk](https://user-images.githubusercontent.com/63316070/236689153-c479b8e2-b809-464a-8408-64a6b4b35e8c.png)

  - The most active users is in a company "Red", the least users is in a company "Green"
  - 38,56% of users did't register

### 3. Analysis active and inactive users <a name="3"></a>
  
![vk2](https://user-images.githubusercontent.com/63316070/236689198-9320c65c-8e8e-43dc-b627-69e4a14164aa.png)

  - 6.67% of users Red company wasn't active
  - 39.61% of users Blue company wasn't active

### 4. Creation of correlation matrix <a name="4"></a>

![vk3](https://user-images.githubusercontent.com/63316070/236689236-6888d0e5-f47b-4f2f-9a38-bdd7f497f91d.png)

- A strong correlation equals 0.95 between "Green_gvm_order_count" and "Green_gvm_total"
- A strong correlation equals 0.91 between "Black_gvm_order_count" and "Black_gvm_total"

### 5. Analysis device activity <a name="5"></a>

**Plot with all companies**

![vk4](https://user-images.githubusercontent.com/63316070/236689394-d2ca3a4d-46bf-4295-b6bd-70fc8f9e08a5.png)

**Plot without Red company**

![vk5](https://user-images.githubusercontent.com/63316070/236689396-c6c6c2c3-c259-444b-be8b-34d82479be8c.png)

- In the Red company the most popular device is Web
- In the Black company all device activity is common
- In the Blue company the most popular devices are Web and Android
- In the Green company there are a lot of unknown devices. If you don't into account unknown devices, then the most popular devices are Android and Apple (mobile)

### 6. Analysis gvm statistics <a name="6"></a>

**Important!** Red company hadn't information about gvm and exclude from analysis. 

**Result. Rate of companies by GVM:**  
  1. Black 
  2. Green 
  3. Blue

### 7. Check influence "is_msk" column on gvm activity <a name="7"></a>

Used test - [**Freeman-halton test**](https://www.ine.pt/revstat/pdf/Performancecomparisonofindependencetests.pdf)

**Important! Installation of rpy.**

Write in Conda terminal:

```conda
pip install rpy2
```

Write Hypothesis: 

H0: is_msk and company_gvm_total - same (not affect)
H1: is_msk and company_gvm_total - different (affect)

Conclusions:
1. **Black company**. H0 is rejected. "is_msk" column **affects** on gvm value
2. **Green company**. H0 is accepted. "is_msk" column **doesn't affect** on gvm value
3. **Blue company**. H0 is accepted. "is_msk" column **doesn't affect** on gvm value





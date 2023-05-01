# Olist Shipping Analysis

This is a repository for a Python project examining the factors behind delivery outcomes and customer satisfaction on a Brazilian ecommerce platform, Olist.

**Objective**

Olist is a Brazilian e-commerce platform that connects merchants to customer markets across Brazil via its SaaS licensing model that provides small, brick-and-mortar businesses. In order to continue to grow, Olist must focus on the customer experience throughout Brazil by offering improved fulfillment services to sellers and buyers across the nation. This project analyzes overall delivery times in light of geography, product types, price, weights, and costs and considers the different components of the fulfillment process. Key questions answered by this project:

                -In which states are customers and sellers facing the longest fulfillment times?
                -Which portions of the fulfillment process take the longest time?
                -Where do the approval-to-order and order-to-shipper portions of the fulfillment process take the longest?
                -What is the effect of order prices on shipping times?
                -Where are the customers purchasing the most expensive items? Where are the merchants selling the most expensive items? 
                -What are the average freight costs in each state?
                         

**Data**

I started with a collection of nine (9) different csv files of related data, all connected by different fields. The data covered product weight, prices, shipping times, seller information, customer information, product categories, geographies and more. This data was made publicly-available on Kaggle and the original link may be found [here] (https://www.kaggle.com/olistbr/brazilian-ecommerce).


**Analysis**

I first examined the strength of the correlations between selected factors of interest, mostly pertaining to delivery time and customer satisfaction metrics. The stronger factors became the focus of the analysis, namely: Product Price and Freight Value; Estimated Fulfillment Time and Total Fulfillment Time; Order-to-Carrier Time and Total Fulfillment Time; Product Price and Freight Value; and Total Fulfillment Time and Customer Review Score.

I also mapped Review Scores, Delivery Times, Prices, Freight Values, Order-to-Approval Lag Times, and Order-to-Carrier Lag Times for both Sellers and Customers by state. Crucially, I was able to break out different states by their respective market size as the differences in volume are so vast as to preclude meaningful comparisons between large states like Sao Paulo and more peripheral states like Amazonas. I grouped the states into four broad classes based on market size: 'Frontier,' 'Small,' 'Medium,' and 'Large.'

A time series analysis was conducted on a related dataset from the Brazilian Central Bank which tracked the Consumer Price Index (CPI). The prupose of this analysis was to serve as a potential predictor for future transaction volume, as correlations could potentially drawn between fluctuations in the CPI and placed purchase orders. I modified the CPI dataset to include only the data since the 1994 reforms brought the hyperinflation of the 1980s and early 90's into a range which has persisted to the present-day. The data from this more recent period reflects, accurately, the current structural situation faced by Brazilian markets.


**Result**






**Recommendations & Limitations**





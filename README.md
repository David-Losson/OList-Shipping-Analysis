# Olist Shipping Analysis

This is a repository for a Python project examining the factors behind delivery outcomes and customer satisfaction on a Brazilian ecommerce platform, Olist.

##**Objective**

Olist is a Brazilian e-commerce platform that connects merchants to customer markets across Brazil via its SaaS licensing model that provides small, brick-and-mortar businesses. In order to continue to grow, Olist must focus on the customer experience throughout Brazil by offering improved fulfillment services to sellers and buyers across the nation. This project analyzes overall delivery times in light of geography, product types, price, weights, and costs and considers the different components of the fulfillment process. Key questions answered by this project:

                -In which states are customers and sellers facing the longest fulfillment times?
                -Which portions of the fulfillment process take the longest time?
                -Where do the approval-to-order and order-to-shipper portions of the fulfillment process take the longest?
                -What is the effect of order prices on shipping times?
                -Where are the customers purchasing the most expensive items? Where are the merchants selling the most expensive items? 
                -What are the average freight costs in each state?
                         

##**Data**

I started with a collection of nine (9) different csv files of related data, all connected by different fields. The data covered product weight, prices, shipping times, seller information, customer information, product categories, geographies and more. This data was made publicly-available on Kaggle and the original link may be found [here] (https://www.kaggle.com/olistbr/brazilian-ecommerce).


##**Analysis**

I first examined the strength of the correlations between selected factors of interest, mostly pertaining to delivery time and customer satisfaction metrics. The stronger factors became the focus of the analysis, namely: Product Price and Freight Value; Estimated Fulfillment Time and Total Fulfillment Time; Order-to-Carrier Time and Total Fulfillment Time; Product Price and Freight Value; and Total Fulfillment Time and Customer Review Score.

I also mapped Review Scores, Delivery Times, Prices, Freight Values, Order-to-Approval Lag Times, and Order-to-Carrier Lag Times for both Sellers and Customers by state. Crucially, I was able to break out different states by their respective market size as the differences in volume are so vast as to preclude meaningful comparisons between large states like Sao Paulo and more peripheral states like Amazonas. I grouped the states into four broad classes based on market size: 'Frontier,' 'Small,' 'Medium,' and 'Large.'

A time series analysis was conducted on a related dataset from the Brazilian Central Bank which tracked the Consumer Price Index (CPI). The prupose of this analysis was to serve as a potential predictor for future transaction volume, as correlations could potentially drawn between fluctuations in the CPI and placed purchase orders. I modified the CPI dataset to include only the data since the 1994 reforms brought the hyperinflation of the 1980s and early 90's into a range which has persisted to the present-day. The data from this more recent period reflects, accurately, the current structural situation faced by Brazilian markets.


##**Results**

Firstly, it's important to bear in mind the scale of the activity of both selling activity which is primarily concentrated in Sao Paulo. Buying activity is similarly concentrated in Sao Paulo although to a lesser degree. Fulfillment times are slower in smaller, more distant states on the frontier, although, the causes of these bottlenecks vary among different states. To a large degree, consumers in frontier states buy a higher proportion of hihg-price items as compared to the more central states.


###Fulfillment

Unsurprisingly, overall fulfillment times are slower in the western and northeastern regions of the country which are, naturally, more remote and less densely-populated. It appears that the slow overall fulfillment times in the western interior of the country can just be attributed to its isolation whereas the slow delivery to the northeastern region is more attributable to a breakdown in the order-to-approval process. This is something that should be improved upon to encourage more and faster sales in this region of Brazil. It appears the longer delivery times to the western provinces are more attributable to the slow hand-off from seller to carrier (i.e. the delivery company.) This is also a serious issue in the relatively populous and centrally-located State of Paraná in the south (est. pop. 11.5M.) Because Parana is such a large market, we should address the issues sellers are having with decent carrier access and figure out solutions to address the bottleneck.

Customers in Minas Gerais(MG) and Parana(PR) face the longest gaps between ordering a product and receiving approval. These are not insignificant markets in terms of size, so there are some real issues causing this gap whether that's atatributable to variable internet access, glitches in the platform that are unique to customers in those regions (perhaps consumers in those states are more likely to access the platform using mobile or non-mobile devices than those customers in the rest of the country), differences in payment type, or seller difficulties in accessing the purchase orders- the origin of these problems should be identified.

Unsurprisingly, customers in our frontier markets in the north and west also had slightly higher lag times between ordering and receiving approval but this was still less pronounced than the phenomenon observed in the larger states mentioned above.


###Prices

Generally, sellers in Minas Gerais (MG) and Santa Catarina (SC) are selling higher-priced products than in nearby Sao Paulo, Rio Grande do Sul, Bahia, Espirito Santo, or Parana. Some of the northeastern states also have sellers producing relatively high-price products but their numbers are much smaller than those seen in MG or SC, so they should be understood as small sample markets.

Interestingly, consumer price preferences are quite standard across the country with no serious regional tendencies towards certain price ranges. Once again, customers in a few, small frontier markets in the far northeastern corner of the country exhibit a prefence towards higher-price purchases. Compared to consumers in the larger states who order products across the different price ranges, consumers in frontier states tend to purchase more high-price items, indicating that customers may only purchase those big-ticket items that can justify the long wait times and high shipping costs.


###Freight

The price of freight (i.e. "freight values") closely matches up with the map of overall fulfillment times by state. Here as there, sellers in the western and northeastern states experience the most costly shipping prices while sellers in the core populated regions of the country along the southeastern coast encounter the lowest rates. This is largely a function of where the buyers are and they are mostly concentrated in that southeastern coastal region.

Similar to the situation faced by sellers, consumers face higher shipping costs (i.e. "freight value") in the northeast and far western regions of the country and comparatively low freight costs in the southeastern coastal core of the country with the notable exceptions of Brasilia, Rio de Janeiro, and Minas Gerais- all of which are significant markets facing steeper shipping costs than in comparable, neighboring states like Sao Paulo, Goias, and Espirito Santo.

Other heavily-populated states with the potential to become large, mature markets like Bahia and Pernambuco are at present constrained by the long wait times and high costs of shipping that await consumers and sellers. Still, efforts should be made to encourage cheaper and more expeditious freight carrier route planning from more remote regions as this would make sellers in those regions more competitive, thereby expeanding our pool of sellers.


###Reviews

There's not a clear geographic variation in satisfaction with sellers' products. Customer satisfaction, as expressed through review ratings, is relatively high and uniform throughout the country in big, small, medium, and "frontier" states in every region of the country. Similarly, there's not a particularly strong geographic assocation between consumers' locations and their satisfaction with their pruchases- it's relatively high and consistent across the various states and regions of the country with the notable exceptions of Goiás(GO), Minas Gerais(MG), and Brasilia(BSB) in the southeastern interior of the country and Pernambuco in the northeast.

In the case of GO, MG, and BSB, they are larger states, in terms of order volume, so there may be some very real issues in terms of service or product quality perceived by customers in those regions. In the case of Pernambuco which is a frontier market, the results should be considered less definitive.


##**Recommendations & Limitations**

Efforts to connect potential sellers in small and frontier states with a wider number of shipping companiess could be a good catalyst for market expansion and maturation of the Olist marketplace in those places. Connecting would-be sellers with carriers would simultaneously create the access to shipping options that make participation on the platform more cost-effective while creating a viable market that allows the shippers themselves to enter those states.

In frontier states, we could offer bundle & save freight discounts and bulk order price promotions for consumers making big purchases, to encourage more low-price, high-volume sales along with their big-ticket purchase.

Further studies into the lag between placement of an order and approval of a pruchase should be conducted for consumers in Minas Gerais and Parana, where this lag is pronounced. Efforts should be made to pinpoint the source of this lag- is it a malfunction in the platform itself? Is this a function of internet speed and access in those regions? Are the commonly-used methods of payment slowing down the approval processes in those regions? 

We should interview customers in Goias, Minas Gerais, and Brasilia Federal District to understand the causes behind lower-than-expected customer satisfaction.

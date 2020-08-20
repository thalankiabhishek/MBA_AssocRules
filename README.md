# __Instacart Orders__
_The dataset for this competition is a relational set of files describing customers' orders over time. The goal of the competition is to predict which products will be in a user's next order. The dataset is anonymized and contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. For each user, we provide between 4 and 100 of their orders, with the sequence of products purchased in each order. We also provide the week and hour of day the order was placed, and a relative measure of time between orders._

### Data Dictionary

1. orders (3.4m rows, 206k users):

  * order_id: order identifier
  * user_id: customer identifier
  * eval_set: which evaluation set this order belongs in (see SET described below)
  * order_number: the order sequence number for this user (1 = first, n = nth)
  * order_dow: the day of the week the order was placed on
  * order_hour_of_day: the hour of the day the order was placed on
  * days_since_prior: days since the last order, capped at 30 (with NAs for order_number = 1)
  
2. products (50k rows):
  * product_id: product identifier
  * product_name: name of the product
  * aisle_id: foreign key
  * department_id: foreign key
  
3. aisles (134 rows):
  * aisle_id: aisle identifier
  * aisle: the name of the aisle
  
4. deptartments (21 rows):
  * department_id: department identifier
  * department: the name of the department
  
5. order_products__SET (30m+ rows):
  * order_id: foreign key
  * product_id: foreign key
  * add_to_cart_order: order in which each product was added to cart
  * reordered: 1 if this product has been ordered by this user in the past, 0 otherwise
  * where SET is one of the four following evaluation sets (eval_set in orders):

    1. "prior": orders prior to that users most recent order (~3.2m orders)
    2. "train": training data supplied to participants (~131k orders)
    3. "test": test data reserved for machine learning competitions (~75k orders)


For more information, see the blog post accompanying its public release.
[Blog](https://tech.instacart.com/3-million-instacart-orders-open-sourced-d40d29ead6f2)
[Data](https://www.instacart.com/datasets/grocery-shopping-2017)

>*The dataset is provided as-is for non-commercial use and is subject to Instacart's Terms of Service.*


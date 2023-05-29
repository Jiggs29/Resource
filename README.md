import requests

import bs4


request1 = requests.get('https://www.flipkart.com/redmi-10-midnight-black-64-gb/p/itmd93641e4ebb47?pid=MOBGC9GYEBH3GZ4E&lid=LSTMOBGC9GYEBH3GZ4E44YY0L&marketplace=FLIPKART&fm=productRecommendation%2Fsimilar&iid=R%3As%3Bp%3AMOBG73E7GKQK4KZP%3Bpt%3App%3Buid%3Aac8a3859-f4de-11ed-aa73-955faf22b2d0%3B.MOBGC9GYEBH3GZ4E&ppt=pp&ppn=pp&ssid=smh40m1g000000001684347262906&otracker=pp_reco_Similar%2BProducts_3_35.productCard.PMU_HORIZONTAL_REDMI%2B10%2B%2528Midnight%2BBlack%252C%2B64%2BGB%2529_MOBGC9GYEBH3GZ4E_productRecommendation%2Fsimilar_2&otracker1=pp_reco_PINNED_productRecommendation%2Fsimilar_Similar%2BProducts_GRID_productCard_cc_3_NA_view-all&cid=MOBGC9GYEBH3GZ4E')

request1

request1.content 

soup = bs4.BeautifulSoup(request1.text)

soup

#Fetching Reviews/Comments

reviews = soup.find_all('div',{'class' : 't-ZTKy'});

for review in reviews:

print(review.get_text() + "\n\n")





#Average Overall rating

ratings = soup.find('div',{'class':'_3LWZlK'}).get_text();

print(ratings)





#Individual ratings

individual_ratings = soup.findAll('div',{'class':'_3LWZlK _1BLPMq'});

for indi_rating in individual_ratings:

print(indi_rating.get_text() + " \n")



#Fetching tags

tags = soup.find('span',{'class':'yhB1nd GXgmTe'}).get_text();

tags



#Fetching Customer Names

customer_name = soup.findAll('p',{'class':'_2sc7ZR _2V5EHH'});

for cust_name in customer_name:

print(cust_name.get_text() + " \n")











# database
Import requests
From bs4 import beautiful soup
Import pandas
Import argparse
Import connect 
Praser=argprase.ArgumentParser()
Praser.addargument("--page_num_max",help="enter the number of pages to praise",type=int")
Prayer.add_argument("--dname",help ="enter the name of db",type=str)
args=prayer.parse_args()
Oyo_url="https://www.oyorooms.com/hotels-in-banglore/?page="
Page_num_MAX=args.page_num_max
Scraped_info_list=[]
Connect.connect(arts.dbname)

For page_num in range(1,page_num_MAX):
  URL=oyo_url+str(page_num)
  print("GET Request for :"+URL)
  Req=request.get(url)
  Content = req.content

   Soup =Beautiful soup(content,"html.praser)

   All hotels =soup.find_all("div",{"class":"hotelcaristing"})
   For hotel in all hotels:
    Hotel_dict={}
    Hotel_dict["name"]=hotel.find("h3",{class":"listhoteldescription"}).text
    Hotel_dict["address"]=hotel.find("span",{"itemprop:"Street address"}).text

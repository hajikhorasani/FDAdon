
# An Affordable Food Donation Platform

By Shahin Hajikhorasani

Hunger, poverty and food prices are linked. Not every poor person is hungry, but almost all hungry people are poor. Millions live with hunger and undernourishment because they cannot afford to buy enough food, cannot afford nutritious foods or cannot afford the farming supplies they need to grow enough good food of their own.
 Hunger is often observed as the most severe appearance of poverty. It is also a concept that is often connected with poor, developing countries, but it has also become increasingly common in the developed countries like the United States and few countries in the EU, also in the fairly well-off countries such as Iran and its neighbors.
In 2014, 5.6 percent of U.S. households (6.9 million households) had very low food security. In this more severe range of food insecurity, the food intake of some household members was reduced and normal eating patterns were disrupted at times during the year due to limited resources. (Based on USDA Household Food Security in the United States in 2014)
The most important obstacle in donating money to the hungry people around the world is that a large amount of donors think the needy will use that money for unethical behaviors or illegal substances instead of buying food, drink or providing other essential items such as hygiene, clothing, health and shelter. Thus, they usually refuse to donate cash to the homeless or poor.

## What we can do to reduce the food insecurity

The main idea behind this article is to provide an information technology-based approach in reducing hunger among homeless and destitute people.

Current solutions for metropolitan hunger are not efficient due to the variety of issues and difficulties as follows:

- Ability of charities which use traditional methods to receive donations to prepare and distribute food is limited to a small number of hungry people.
- In many cases, lack of financial transparency and complexity of the audit in the charities, make the donors not trust them.
- Usually providing financial and human resources to operate multiple facilities in different parts of the city to distribute food, is not practical. As a result, organizations have to distribute food in specific and limited areas of a town.
- Procurement of supplies, and cooking food for the hungry metropolises require complicated mechanisms and very large organization with unlimited financial resources.
- Conventional methods of raising money by charities will not be accountable to the problem of hunger.

As the resolution, this proposal takes advantage of current infrastructures of Food Delivery Apps (Online Food Ordering Companies) such as Doordash, Grubhub, UberEATS, SnappFood, Reyhoon, and Chillivery, and it could cost as little as a QR code printer for their data centers.
On this platform, Food Delivery Apps which sell food and drink from cafes, restaurants, or supermarkets, also sell QR chips (printed QR codes) at different prices. The customer - which could be a donor - purchases these chips online and donates them (after receiving them by restaurant's delivery) to the needy, its friends, younger family members such as children, or just chooses from the app to donate the chips to charities or the needy by the Food Delivery App itself.
Since the cafes, restaurants, or supermarkets use the merchant version of Food Delivery Apps to accept orders, they already have at least one smartphone with a built-in camera. The restaurants give the food and drink to the holder of QR chip after they've validated the chip, and the equivalent cost of the chip will be received from the Food Delivery Apps by the restaurant.
 
In this method, there is no possibility of the sale of chips by the needy, because the chips could be used just inside the restaurant to buy food and drinks. Also, since the chips are small and could be the same size of cash, they are portable and can be used at any time instead of money to donate to the homeless and hungry. Parents can also offer these chips instead of cash to their children to reduce the risk of them buying cigarettes or drugs.
In some cases, the price of food may not be consistent with the amount on the chips. Knowing that cash is not being given to the person that redeemed the chip, the following are two methods in dealing with the excess on the chips:

First, if the restaurant could provide extra food or drinks to the amount of excess remaining on the chips; secondly, the excess will be returned to the Food Delivery Service, and the equivalent will be redistributed to those in need.

For example, one person drops $20 a chip, and food and drinks are charged at $14 at checkout. The restaurant could recommend the customer get items that would cost or come close to the remaining amount, or the $6 goes back into an account of Food Delivery Service. When that account accumulates the smallest amount a chip could be (for example. $10), a non-salable chip will be printed and redistributed to those in need.

# Benefits of the proposed platform are the following:

- People will trust this new donation platform because it reduces the risks of money donation.
- The cost of setup and maintenance of the platform is very low, because there is no need to establish an organization to procure the supplies, and prepare and distribute the foods. Also all the requirements including the restaurants and Food Delivery Apps' infrastructures are currently available.
- The cost of distribution will be completely removed as the needy will go to the restaurant in-person to get it food and drinks.

In addition of the above-mentioned items, other benefits for the restaurants and Food Delivery companies are:

- More people (the donors) install and use the Food Delivery App.
- Food Delivery companies can advertise on the chips and on the tags for the restaurants.
- More restaurants join the Online Food Delivery ecosystem.
- More foods will be sold to the customers, consequently, more farming supplies will be consumed

# Superficial look at the technical details

There are three options to issue the QR chips in this platform:

1. Centralized printing by the Food Delivery Company
2. Distributed printing by the restaurant's invoice printer
3. Distributed printing by the restaurants’ distinguished QR code printer

The advantage of centralized printing by the Food Delivery Company is that just slight changes need to be done in the software and there will be a QR code printer in the company. In this model, the company prints the chips at varied prices and distributes them to the restaurants.
It's better to give a tag to the restaurant at the time of delivery of the chips to them. The tag should indicate that this restaurant accepts chips, thus the chip holder can find these kinds of restaurants easily.

The QR code includes the following items:

- Chip publisher information
- Date of issue and validity
- Value of the chip
- Unique Identifier
- Reserved field

All the above items together as a TBS will be signed digitally by the chip publisher, and the signature is inserted to the QR code. The digital signature algorithm should be RSA with key length of 2048 bit or ECDSA with elliptic curve 'brainpoolp256t1' or 'brainpoolp384t1'. Due to the limited amount of data that can be held in a QR code and its visibility, it is better to use the ECDSA with key length 256 bit, if you need to store more than 600 characters of data in the QR code.
 
 The private key of the chip issuer, should be generated inside a hardware that can protect the private keys. In the centralized printing by the Food Delivery Company model, using a HSM with PKCS #11 support and certified by FIPS 140-2 Level 3 is advocated. And in the distributed printing by restaurants model, using hardware tokens with at least FIPS 140-2 Level 2 certificate, is recommended.

The restaurant after receiving this chip, puts it in front of the smartphone's camera. Then the merchant version of the Food Delivery App reads the QR code and extracts the information including the digital signature from it. After that the application sends the digital signature alongside other information to the Food Delivery Server to validate the digital signature and check that the chip is a sold one. If the Food Delivery App approves the validity of the chip, then restaurant gives the food and drink to the chip holder and charges the Food Delivery Company.

# This platform also could be used for donating clothing, cleaning supplies and educational materials. It is also possible to use this platform to donate temporary shelters to the homeless by paying the rent of shelter with the chips.


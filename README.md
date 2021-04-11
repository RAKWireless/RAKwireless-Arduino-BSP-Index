# RAKwireless BSP Support For The Arduino Board Manager
| ![RAKwireless](./assets/RAK-Whirls.png) | ![RAKstar](./assets/rakstar.jpg) | ![WisBlock](./assets/WisBlock.svg) |
| :-: | :-: | :-: |

----

_**This repo contains the custom `package_rakwireless_index.json` files that can be used to add new
third party boards to the Arduino v1.6.4+ IDE.**_

----

## Supported WisBlock Core modules

This repository contains support for the following RAKwireless Arduino BSP's for the following [WisBlock Core modules](https://docs.rakwireless.com/Product-Categories/WisBlock/#wisblock-core).

- **[RAK4631](https://docs.rakwireless.com/Product-Categories/WisBlock/RAK4631/Overview/#product-description)**    
- **[RAK11200](https://docs.rakwireless.com/Product-Categories/WisBlock/RAK11200/Overview/#product-description)**

----

## Installation instructions for _RAKwireless WisBlock Core_ modules

To add board support for our products, start Arduino and open the Preferences window (**File** > **Preferences**).     

![Preferences](./assets/01-add-bsp-url.png)     

----

In the **Preferences** window, look for **Additional Boards Manager URLs** and click the icon on the right side.

![Additional Boards Manager URLs](./assets/02-add-bsp-url.png)  

----

Copy `https://raw.githubusercontent.com/RAKwireless/RAKwireless-Arduino-BSP-Index/main/package_rakwireless_index.json` and paste it into the new window.      
- If there is already an URL from another manufacturer in that field, paste the above URL into a new line.    

![Paste](./assets/03-add-bsp-url.png)  

Then press the **OK** button.

----

Next open the **Boards Manager** in the menu **Tools**    
![Preferences](./assets/04-add-bsp.png) 

----

Write "RAK" (without quotes) in the search bar. The RAKwireless WisBlock Core modules will be shown in the window.  
  
![Preferences](./assets/05-add-bsp.png) 

You can see which BSP is required for which WisBlock Core module.     
Select the BSP you need for your WisBlock Core module and click on **Install**.    

_**Depending on your connection speed, the installation can take some time. Please be patient.**_

----

**RAKwireless invests time and resources providing this open source code, please support RAKwireless and open-source hardware by purchasing products from [RAKwireless](https://rakwireless.com)!**

**_For support and questions about RAKwireless products please visit our [forum](https://forum.rakwireless.com/)    
For examples and quick start tutorial please visit our [Github Repo](https://github.com/RAKWireless/Wisblock)    
For additional information about RAK products please visit our [Documentation Center](https://docs.rakwireless.com/Product-Categories/WisBlock/)    
To buy WisBlock modules please visit our [online store](https://store.rakwireless.com/pages/wisblock)_**



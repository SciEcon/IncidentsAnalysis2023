# The Impact of Incidents on Crypto Markets: An Analysis of CeFi and DeFi Trust Mechanism 

## *Supplementary resources, data, and code*
by **Xintong Wu**, **Wanlin Deng**, **Yutong Quan** and **Luyao Zhang***

(* *the corresponding author: lz183@duke.edu*)

<img src="https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Images/whole_structure.png" width="600" alt="article-overview" /><br/>

*Figure 1. Overview of the article: created by [Miro](https://miro.com/).*

## Table of Contents
- [Data](https://github.com/SciEcon/IncidentsAnalysis2023/tree/main#data)
- [Code](https://github.com/SciEcon/IncidentsAnalysis2023/tree/main#code)
- [Images]()
- [Reference](https://github.com/SciEcon/IncidentsAnalysis2023/tree/main#references)

## Data
<img src="https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Images/Data_collection.png" alt="data-collected-flowchart" /><br/>

*Figure 2. Data collected flowchart: created by [Whimsical](https://whimsical.com/).*

### Collected Data

For collecting data from the flipside, please refer to [**flipsidecrypto.xyz**](https://flipsidecrypto.xyz/siavashj/cex-to-dex-and-dex-to-cex-cex-to-dex-and-dex-to-cex-arIDpY).

#### Meta Data Infomation

| Data Files  | Data Type | Data Content |
| ------------- | ------------- | ------------- |
| [1_Price.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/collected/1_Price.csv)  | Queried  | WETH Daily Price  |
| [2_CEX_to_DEX.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/collected/2_CEX_to_DEX.csv)  | Queried  | CEX to DEX Transaction Flow  |
| [2_DEX_to_CEX.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/collected/2_DEX_to_CEX.csv)  | Queried  | DEX to CEX Transaction Flow  |
| [2_Netflow.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/collected/2_Netflow.csv)  | Queried  | NetFlow  |

#### Data Dictionary
- **WETH Daily Price**

| Variable Name          | Description           | Frequency | Unit | Type |
|------------------------|-----------------------|-----------|------|------|
| DATE                   | Date of price      | Daily     | Date | Date |
| Price                  | Daily price of WETH   | Daily     | USD | Numeric |


- **Transaction between CEX and DEX**
 
| Variable Name          | Description           | Frequency | Unit | Type |
|------------------------|-----------------------|-----------|------|------|
| DATE                   | Date of transfer      | Daily     | Date | Date |
| N\_TRANSFER            | Number of transfers   | Daily     | Count| Integer |
| USER                   | User identifier      | Daily     | Count | Integer |
| AMOUNT\_USD            | Amount in USD         | Daily     | USD  | Numeric |
| AMOUNT\_ETH            | Amount in ETH         | Daily     | ETH  | Numeric |
| CEX                    | Centralized Exchange  | Daily     | Text | Categorical | 
| DEX                    | Decentralized Exchange| Daily     | Text | Categorical |


- **Netflow between CEX and DEX**
  
| Variable Name         | Description            | Frequency | Unit     | Type    | 
| --------------------- | ---------------------- | --------- | -------- | ------- |
| DATE                  | Transaction Date       | Daily     | Date     | Date    | 
| USER $\rightarrow$ DEX | User Interaction with DEX | Daily  | Count    | Integer |
| USER $\rightarrow$ CEX | User Interaction with CEX | Daily  | Count    | Integer |
| Net User              | Net User Interaction    | Daily     | Count    | Integer |
| Amount $\rightarrow$ DEX | Amount Related to DEX | Daily | USD      | Numeric |
| Amount $\rightarrow$ CEX | Amount Related to CEX | Daily | USD      | Numeric |
| Net Amount ETH        | Net ETH Amount          | Daily     | ETH      | Numeric |
| Amount \$ $\rightarrow$ DEX | Amount in USD Related to DEX | Daily | USD | Numeric |
| Amount \$ $\rightarrow$ CEX | Amount in USD Related to CEX | Daily | USD | Numeric |
| Net Amount \$         | Net USD Amount          | Daily     | USD      | Numeric |


### Analyzed Data

#### Meta Data Infomation

| Data Files  | Data Type | Data Content |
| ------------- | ------------- | ------------- |
| [1_price_statistics_data.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/analyzed/1_price_statistics_data.csv)  | Analyzed  | statistics data of WETH daily price |
| [2_cex_to_dex_statistics_data.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/analyzed/2_cex_to_dex_statistics_data.csv)  | Analyzed  | statistics data of CEX to DEX transaction flow  |
| [2_dex_to_cex_statistics_data.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/analyzed/2_dex_to_cex_statistics_data.csv)  | Analyzed  | statistics data of DEX to CEX transaction flow  |
| [2_netflow_statistics_data.csv](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Data/analyzed/2_netflow_statistics_data.csv)  | Analyzed  | statistics data of NetFlow   |


#### Data Dictionary
- **WETH Daily Price**

| Variable Name          | Description           | Frequency | Unit | Type |
|------------------------|-----------------------|-----------|------|------|
| DATE                   | Date of price      | Daily     | Date | Date |
| Mean_PreviousMonth    	|Mean price of Previous Month|	Monthly|	USD|	Numeric|
| Mean_NextMonth	        |Mean price of Next Month| Monthly|	USD|	Numeric|
| Mean_Difference	       |Price difference between Next Month and Previous Month	|Monthly	|USD	|Numeric|

- **Transaction between CEX and DEX**

| Variable Name          | Description           | Frequency | Unit | Type |
|------------------------|-----------------------|-----------|------|------|
| DATE                   | Date of transfer      | Daily     | Date | Date |
| Mean_PreviousMonth    	|Mean transaction of Previous Month|	Monthly|	USD|	Numeric|
| Mean_NextMonth	        |Mean transaction of Next Month| Monthly|	USD|	Numeric|
| Mean_Difference	       |Transaction difference between Next Month and Previous Month	|Monthly	|USD	|Numeric|


- **Netflow between CEX and DEX**

| Variable Name          | Description           | Frequency | Unit | Type |
|------------------------|-----------------------|-----------|------|------|
| DATE                   | Date of transfer      | Daily     | Date | Date |
| Mean_PreviousMonth    	|Mean newflow transaction of Previous Month|	Monthly|	USD|	Numeric|
| Mean_NextMonth	        |Mean newflow transaction of Next Month| Monthly|	USD|	Numeric|
| Mean_Difference	       |Newflow transaction difference between Next Month and Previous Month	|Monthly	|USD	|Numeric|

## Code
| **Code Type** | **Google Colab File Name**|
| ------- | ------- |
| Collection | [Data_Collection.ipynb](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Code/Data_Collection.ipynb) |
| Analysis | [Data_Analysis.ipynb](https://github.com/SciEcon/IncidentsAnalysis2023/blob/main/Code/Data_Analysis.ipynb) |

## Images

### Price
<table>
    <tr>
        <td><img src="./Images/Price.png" alt="price"></td>
        <td><a href="./Images/Price.png">./Images/Price.png</a></td>
    </tr>
</table>

### Transaction Flow
<table>
    <tr>
        <td> DEX to CEX </td>
        <td><img src="./Images/DtC.png" alt="dex-to-cex"></td>
        <td><a href="./Images/DtC.png">./Images/DtC.png</a></td>
    </tr>
    <tr>
        <td> DEX to CEX </td>
        <td><img src="./Images/CtD.png" alt="cex-to-dex"></td>
        <td><a href="./Images/CtD.png">./Images/CtD.png</a></td>
    </tr>
    <tr>
        <td> NetFlow </td>
        <td><img src="./Images/Net.png" alt="NetFlow"></td>
        <td><a href="./Images/Net.png">./Images/Net.png</a></td>
    </tr>
</table>

### Exchanges Trading Process
<table>
    <tr>
        <td> Binance WETH trading process </td>
        <td><img src="./Images/Binance.png" alt="binance"></td>
        <td><a href="./Images/Binance.png">./Images/Binance.png</a></td>
    </tr>
    <tr>
        <td> Uniswap WETH trading process </td>
        <td><img src="./Images/Uniswap.png" alt="uniswap"></td>
        <td><a href="./Images/Uniswap.png">./Images/Uniswap.png</a></td>
    </tr>
</table>


## References
**Data Reference:** flipsidecrypto ( https://flipsidecrypto.xyz/)

**Code Reference:** flipsidecrypto/siavashj (https://flipsidecrypto.xyz/siavashj/q/1sPLGdSteDlQ)




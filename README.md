---
description: End-to-end blockchain analytics on Solana
---

# 👋 Welcome

## About Us

Top Ledger is positioned as a comprehensive blockchain analytics platform on Solana, catering specifically to web3 data teams, institutions and market intelligence platforms. It emphasizes the elimination of concerns related to data integrity, speed, and the need for infrastructure customization.

The platform is designed to serve the needs of research and analysis in the blockchain space, providing end-to-end solutions that streamline the process of accessing and interpreting complex blockchain data.



When wallets are most active in trading (time of day, day of the week)?

Why have wallets been deactivated, how long they remain inactive, and whether they switch to other platforms? Look into wallets that become active again, especially their first activity after coming back.

How can we categorize wallets by their willingness to take risks, shown by the kinds of loans they choose, such as those with more collateral versus less, or short-term compared to long-term?

## Products

### 1. SQL Based Analytics Platform

Our backend pulls raw data from Solana daily, labels, indexes it into tables, and maintains a historical archive for easy querying, empowering you to create in-depth metrics effortlessly.

We decode the Solana program data and segregate it program wise so that you focus on generating deeper insights. We do it by going into each program’s rust codebase and mapping every function and its arguments.

Finally create meaningful graphs, powerful dashboards and present it as you like.

<figure><img src=".gitbook/assets/Screenshot 2024-02-23 at 6.08.37 PM.png" alt=""><figcaption><p>Sample query to calculate daily NFT trade volume</p></figcaption></figure>

#### Top Ledger Supports Trino SQL Syntax

Trino is a ludicrously fast distributed SQL query engine that helps you explore your data universe.

Visit [https://trino.io/](https://trino.io/) for more info

[Here](https://www.starburst.io/wp-content/uploads/2020/07/Presto-Training-Series-Advanced-SQL-Features-in-Presto.pdf) is a great presentation on how to write advance SQL queries in Presto.

Also, a detailed documentation about the syntax and methods is available [here](https://trino.io/docs/current/).

Don't worry we have provided enough sample queries for you to get accustomed to it quickly and easily.

#### Visualization Suite

See the big, easy to digest picture for in-depth understanding and data driven decision making. Use our visualization suite to present any metric in a clear and precise way.

Transform complex tables into meaningful and beautiful charts as shown below:&#x20;

<figure><img src=".gitbook/assets/Screenshot 2024-02-23 at 6.28.02 PM.png" alt=""><figcaption><p>Sample table showing weekly trades and trade volume for different markets on Phoenix</p></figcaption></figure>

<figure><img src=".gitbook/assets/Screenshot 2024-02-23 at 6.34.15 PM.png" alt=""><figcaption><p>Above trade volume table converted into a meaningful chart</p></figcaption></figure>

The bar chart visualization makes it clear that week of Dec 11th  had the highest trade volume, and helps the audience see the trend over time.

We offer a ton of visualizations to cater to all major analytics needs. Plus a lot more:

* Zoom In & Zoom Out any visualization with ease.
* Refresh your dashboards at your will or schedule the refresh.
* One click share widgets or dashboards with your internal team or with your community.
* Ability to cast the dashboard on your website with your UI/UX  using our [react component](developer-docs/integrate-topledger-dashboards.md).
* Set alerts on any metric to get notified on Slack or on Discord.
* Download data as CSV for further analysis.

#### Powerful Dashboards

A picture is worth a thousand words & a dashboard is worth a million data points. Great stories are the perfect blend of data, visuals and content. This is where dashboards come into play. Data visualizations you create by writing queries, can be placed together to connect the dots and build a meaningful story to present in front of stakeholders, customers, investors, etc.

As an example, in the dashboard below, the first chart depicts the total swap volume since Jan 2023 for DEX ecosystem on Solana. Second one is giving a different perspective by showing daily swap volume for all DEXs while the third one is showing cumulative trends of the volume over the same time period. The fourth and fifth chart depicts the monthly trends and share of respective DEX platform in the total swap volume.  Overall the audience is getting a bird eye view of the DEX ecosystem on the Solana blockchain.

<figure><img src=".gitbook/assets/Screenshot 2024-02-23 at 6.37.49 PM.png" alt=""><figcaption></figcaption></figure>

A beautiful dashboard like above, once created can be published and shared with anyone at a click of a button.

#### Competitive Analysis

With an extensive archive, updated schemas,  wallet mappings, and ecosystem wide data for different ecosystems such as DEXs, Liquid Staking, NFT Trading, DePIN, Perpetuals, etc. Top Ledger facilitates different teams to conduct in-depth competitive analyses effortlessly, providing a comprehensive understanding of their position and standing within their respective ecosystem.

For instance in the case of DEXs there are many big platforms in the landscape such as Raydium, Orca,  Lifinity, Phoenix, etc. And they are interested in knowing not only their own position but also the detailed breakdown of their competitors. Top Ledger help them in getting a clear picture of the entire ecosystem, helping different teams to assess and judge their own and others strengths and problems.&#x20;

<figure><img src=".gitbook/assets/Screenshot 2024-02-24 at 5.19.13 PM.png" alt=""><figcaption><p>Table showing swaps and traders for DEXs</p></figcaption></figure>

To give you a glimpse of sector wide analysis lets look at some of  the metrics related to DEX ecosystem with the help of our dashboard. As an example, in the dashboard shown below, the first chart depicts the total swaps since Jan 2023. Second one is giving a different perspective by showing daily swaps for the DEXs while the third one is showing cumulative trends of the swaps over the same time period. The fourth and fifth chart depicts the monthly trends and share of respective DEX platforms by swaps.  In short, one is getting a good picture of the various platforms and their strengths in the said ecosystem.

<figure><img src=".gitbook/assets/Screenshot 2024-02-24 at 5.14.26 PM.png" alt=""><figcaption><p>Ecosystem wide analysis of Solana DEXs</p></figcaption></figure>

### 2. Wallet Behaviour Analytics

The wallet behavior analytics tool comprehensively indexes each Solana wallet, monitoring their engagements across DEXs, NFTs, DePINs, LST protocols, and perpetuals. With dynamic filters, real-time insights, and CSV data export capabilities, this no-code solution empowers platforms to conduct in-depth analyses of wallet behaviors. The tool facilitates the creation of detailed profiles, ultimately supporting alignment with product development strategies.

For example, platforms in the  the DEX ecosystem can, among various other things such as Trading Platform Comparison, Competitor Platform Loyalty, Wallet Reactivity to Market Events  the following metrics, get the following insights

1. **Token Holdings & Patterns:** Smart tables like program\_analysis and token\_holding in the DEX ecosystem provide insights into token category holdings, historical flow, and average holding duration within wallets over time.
2. **Wallet Activity Segmentation:** These smart tables enable teams to categorize wallets based on volume and trade count, offering insights into trading behavior. The tool allows cross-platform activity comparisons and analysis of token category preferences within specific volume or trade count buckets.
3. **Liquidity Provision Analysis:** Teams can assess token-specific and pool-specific contributions by wallets on their platform compared to competitors. This includes evaluating liquidity for specific tokens, analyzing liquidity management through platforms like Kamino Finance, and exploring preferred locations for liquidity provision.
4. **Trade Activity Patterns:** Smart tables provide insights into trade patterns, including preferred tokens, trading times, and typical trade sizes. Teams can analyze trends in buying vs. selling activities across different token categories, examine wallet churn and reactivation, and assess activity following token launches on competitor platforms.

Likewise, for other ecosystems like NFTs, DePINs, and LST protocols, Top Ledger's Platform provides specific analyses and insights. For more details, [click here](https://stitch-shape-34f.notion.site/Wallet-behaviour-analytics-3b3e89e594ec453a8a6b29ff6110eebf).

### 3. Top Ledger for Research

Top Ledger is a robust Solana-focused data solution designed to meet the specific needs of crypto researchers and industry professionals. It emphasizes data integrity, speed, and customization, offering a comprehensive set of features for advanced analytics.

1. **Trusted Data Source:** Top Ledger serves as a reliable data source for advanced use cases, including AI training, crypto research, and DeFi simulation.
2. **Fast and Reliable Decoded Data:** The platform ensures quick, reliable access to decoded Solana data in private clouds, seamlessly integrating with existing systems for enhanced market research and analytics.
3. **Tailored Schemas for Solana Activities:** Top Ledger provides tailored schemas covering a range of Solana activities, such as DEX trades, NFT/cNFT mints and trades, staking, perpetuals, stablecoin activities, and DePIN.
4. **Connected Analytics Experience:** The platform offers a suite of connected analytics features, continually adding new functionalities to fuel decision-making and productivity. Users can set alerts, secure data integrity, and seamlessly integrate dashboards into websites for an enhanced user experience.

Instead of solely relying on our testimonial, try it out firsthand - [click here](https://topledger.xyz/research) to experience it now.

\


\


\













# **Ships: Preliminary Thoughts (Full)**



#### **Project Outline:**



Investigate whether maritime vessel movements can provide useful information about changes in global oil supply, and whether this information can be used to predict movements in crude oil prices. (Could also be applied to gas tankers and prices).

Since oil sources are limited to certain areas of the planet, a substantial proportion of oil that is internationally traded is transported by tanker. As a result, changes in vessel movements, shipping activity, delivery schedules and meteorological patterns can provide information relating to potential disruptions to the supply chain.



Four main areas that can affect the arrival time of crude oil shipments are weather conditions, port congestion, geopolitical developments and unexpected delays in transit, e.g. being slowed down at a choke point. If these developments can be identified before their impact is reflected in the market, they may provide an opportunity to construct trading signals.

This project will investigate the relationship between these events, particularly those relating to maritime activity, and crude oil market behaviour.



#### **Methodology:**



* Data collection: Obtain large quantities of vessel tracking information, including positions, speeds, routes, arrival and departure times, and vessel draught (which can help indicate when a vessel is laden).
* Behavioural analysis: Establish patterns of typical vessel movements and identify unusual activity, delays or changes in these patterns.
* Apply statistical methods to identify the occurrence of significant changes in vessel behaviour or aggregate maritime activity.
* Investigate whether identified changes are associated with subsequent movements in oil prices or volatility.
* Using this framework, develop and backtest historical potential trading signals, accounting for transaction costs, execution delays, and external factors that may affect performance (weather, politics, etc.)



#### **Data Inventory:**



* **Vessel tracking data:** AIS vessel positions, vessel speed, heading, identity, characteristics, voyage information, port activity.  
Sources: MarineTraffic, VesselFinder, Global Fishing Watch.
* **Weather and environmental data:** Winds, storms, general ocean conditions.  
Sources: ERA5 (historical), Windy, Copernicus
* **Commodity market data (essential for testing):** Brent/WTI crude futures, trading volume to assess market activity, bid-ask spreads to estimate execution cost (though this should be low), historical volatility, futures curves to investigate calendar spreads (instead of trading up or down, trade near-term and long-term in opposite directions, trading the difference between them).  
Sources: TradingView, CME, NASDAQ Data Link?
* **Supplementary Data:** Port traffic information (IMF Portwatch), Oil production and inventory levels (EIA, OPEC, satellite tracking for large storage tanks), Geopolitical events (public news and databases), Cargo information (Kpler, S\&P Global), Satellite observations (Copernicus, Sentinel-1)



There is a concern with money required to access some of this data that I haven't taken into account, so alternatives may need to be considered.



Datasets that are essential for backtesting are historical AIS data, crude oil prices, weather data, as well as port activity data. Cargo info may also help.



#### **09/11 Meeting Requirements (Hypotheses, Instruments, Timeframe, Data)**



We now have several **hypotheses** to choose from:



* Abnormal increases in tanker waiting times at export terminals or at chokepoints (Hormuz, Malacca, ...)
* The movement of empty tankers to predict future crude oil demand and anticipated supply.
* Supply reallocation; whether supplies are redirected to a different port or moved into floating storage
* A closer look at floating storage: an increase in floating storage could indicate oversupply or insufficient immediate demand, which could put downward pressure on prices, BUT if another scheduled transport is delayed, ships from floating storage could be used to fill the gap, meaning a drop in prices may not occur as expected. These are just two examples; there are many others.



Out of these, floating storage, route diversion/supply allocation and investigation of chokepoints provide good opportunities for statistical inference, and each could have a noticeable effect on prices in their own right.



The **instrument** to trade is Brent or WTI futures, although it remains to be seen whether to trade directionally or as a calendar spread.



**Timeframe:** If studying chokepoints, most likely shorter-term, hours to days. Port waiting times may have a slightly longer impact horizon, as it may not be immediately apparent whether the delay is long enough to affect expected delivery date. (Also note that tankers do not publicly announce their scheduled time of arrival, so this would have to be estimated from expected time of arrival entered into AIS when the vessel departs.) Destination changes and floating storage could impact the market more gradually, as changes in offshore inventories can take longer to establish and relocating oil can take time. Potentially days to weeks.
Timeframe is an area that should be backtested to find an optimal signal.



**Data** required has already been covered. Most essential is AIS tracking, cargo data, market data, and then supplementary data (weather, port congestion, production, inventories, geopolitical events).


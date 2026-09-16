This project builds an integrated analytics pipeline covering eleven tasks forecasting, risk classification, clustering, anomaly detection, geospatial analysis, and operational decision support  using thirteen months of Dublin Bikes data (7,416,360 timestamped observations across 115 stations).

Models Implemented

Forecasting: XGBoost Regression with R² of 0.967 and MAE of 1.44 bikes (15-min horizon)
Risk Classification: LightGBM with AUC of 0.998 (near-full risk) and 0.990 (near-empty risk)

The gradient-boosted models achieved near-perfect station-risk discrimination and strong short-horizon forecasting accuracy without requiring deep learning or GPU infrastructure, matching or exceeding accuracy reported for deep learning approaches on comparable bike-sharing data.

Key Steps:
Data cleaning and feature engineering on 7.4 million records across 115 stations, including calendar/temporal features (hour, weekday, season, holiday flag) and lag/rolling-average features. K-Means clustering (k=4) grouped stations into behavioral types (residential, office, tourist, low-utilisation), cross-validated with Ward-linkage hierarchical clustering. Anomaly detection combined rolling z-score and Isolation Forest methods, identifying one malfunctioning station (Station 51) out of 115 through a physical-consistency check, independently confirmed via a separate trip-event feature set. Additional modules included Voronoi geospatial coverage analysis, a haversine-distance proximity recommender, STL time-series decomposition, cross-station correlation analysis, and Monte Carlo risk simulation (1,000 simulated 48-hour paths).

Tech Stack: Python, XGBoost, LightGBM, Scikit-learn, Pandas, Folium/OpenStreetMap, K-Means, Isolation Forest, STL decomposition

Dataset: Dublin Bikes station status data (Aug 2024–Aug 2025), 7,416,360 records across 115 stations, integrated with OpenStreetMap geospatial data

# Short_Tall_Tp_Africa
Supporting data and material with the following manuscript:
"Critical importance of tree and non-tree vegetation for African precipitation"

Authors:
Te Wierik, S.A.1,2, Keune, J.3, Miralles, D.3, Gupta, J.2, Artzy-Randrup, Cammeraat, L.H.1, E.E. van Loon.1

1 Institute for Biodiversity and Ecosystem Dynamics, University of Amsterdam, Amsterdam, the Netherlands 
2 Governance and Inclusive Development, University of Amsterdam, Amsterdam, the Netherlands 
3 Hydro-Climate Extremes Lab, Ghent University, Ghent, Belgium

Last update: 09-02-2023

--------------------------------------------------------------------------------------------------------------------------------
DATA 
--------------------------------------------------------------------------------------------------------------------------------

1. FLEXPART_output_all 				Folder containing the precipitation source regions, differentiating between short and tall vegetation, for individual watersheds (NetCDF-file)
						Output files (<iwatershed>_ALLPBL_biascor-attr_linear_hybrid_monthly_1981-2019_E2P_and_T2P_all.nc) correspond with individual watershed numbers (see below).
						Files represent output of moisture tracking framework from Keune et al., 2022. 

2. major_watersheds 				Folder containing shapefile of the major African watersheds from hydroSHEDS  (major_watersheds.shp)

3. masks 					Folder containing:
						- Mask for all major African watersheds (1 degree) (mask_all_1x1_sum.nc) 
						- Mask representing 1) forest loss hotspot region and 2) all cells with > 30% forest loss (1 degree) (mask_forest_loss.nc)
						- Mask representing 1) grass,- range- and cropland loss hotspot regions and 2) all cells with >30% grass-, range- and cropland loss (1 degree) (mask_croppasture_loss.nc).

4. grid_area.nc 				Surface area (m2) of individual gridcells from a 1x1 degree global grid

5. T_tall_short_mean_annual_1981-2019_1deg.nc 	GLEAM-Hybrid monthly total T and E data, global, 1 degree.

6. vegetation-cover_1deg_monthly_1980-2019.nc	MODIS derived vegetation cover fractions of short and tall vegetation and barren soil from MeASURES.
						Original data (0.05 degree) is resampled to 1 degree. 

7. lulc change					Folder containing:
						- Resampled grass,- range- and cropland loss to 1 degree, indicating which areas experienced >30% of LULC change (hotspot0.3_pasture-cropland_loss.tif)
						- Resampled forest loss to 1 degree, indicating which areas experienced >30% of LULC change (hotspot0.3_forest_loss.tif)

--------------------------------------------------------------------------------------------------------------------------------
CODE AND ENVIRONMENT
--------------------------------------------------------------------------------------------------------------------------------

Short_tall_Tp_Africa.py 		Python code to analyze the moisture sources over individual watersheds
					 
Short_tall.yml				Necessary environment to run Short-tall_Tp_Africa.py. Make sure the environment is imported and activated before running the script.
	
--------------------------------------------------------------------------------------------------------------------------------
OUTPUT
--------------------------------------------------------------------------------------------------------------------------------

1. Figure 3		
	t_volumetric.png			3a. Mean annual TP flow from trees (km3 year-1)
	t_normalized.png			3b. Mean annual TP flux from trees (mm year-1)	
	h_volumetric.png			3c. Mean annual TP flow from non-tree vegetation (km3 year-1)
	h_volumetric.png			3d. Mean annual TP flux from non-tree vegetation (mm year-1)	

2. Supplementary figure 2
	extent_t				Contributing source regions of P from trees over the African continent using Tmin (mean annual TP > 0.5 mm yr-1).
	extent_h 				Contributing source regions of P from non-tree vegetation over the African continent using Tmin (mean annual TP > 0.5 mm yr-1)

3. Supporting data
	0.5pshed_output_allwatersheds		CSV file containing output data from all individual watersheds: mean annual contribution of short and tall vegetation (km3/year and mm/year); associated surface area (km2); relative contribution to precipitation from short and tall vegetation (%); relative contribution to dry and wet season precipitation from tall and short vegeation (%) 
	0.5pshed_continental_sum_output.csv 	CSV file containing output data of aggregated means at continental level: mean annual contribution of short and tall vegetation to precipitation over Africa (mm/year and km3/year); associated surface area (km2).
	0.5pshed_hotspot_contributions.csv 	CSV file containing output data of LULC hotspot contributions to precipitation from all individual watersheds: volumetric contribution from hotspot regions (km3); surface area of the hotspot regions (km2); mean annual precipitation (km3/year) and mean annual precipitation from T (km3/year)

----------------------------------------------------------------------------------------------------------------------------
WATERSHED NUMBER REFERENCES:

1	Lake Chad
2 	Nile
3 	Rift Valley
4 	Congo
5 	Niger
6 	Volta
7 	Africa, West Coast
8 	Africa, North West Coast
9 	Mediterranean South Coast
10 	Africa, Red Sea - Gulf of Aden Coast
11 	Shebelli - Juba
12 	Africa, East Central Coast
13 	Madasgacar
14 	Zambezi
15 	Africa, Indian Ocean Coast
16 	Limpopo
17 	South Africa, South Coast
18 	South Africa, West Coast
19 	Orange
20 	Africa, South Interior
21 	Namibia, Coast
22 	Angola, Coast
23 	Gulf of Guinea
24 	Senegal
25 	Africa, North Interior

----------------------------------------------------------------------------------------------------------------------------
REFERENCES & DATA SOURCES

- Keune, J., Schumacher, D.L., and Miralles, D.G. (2022) A unified framework to estimate the origins of atmospheric moisture and heat using Lagrangian models. Geosci. Model Dev., 15, 1875–1898, 2022 https://doi.org/10.5194/gmd-15-1875-2022
- te Wierik, S.A., Keune, J., Miralles, D.G., Gupta, J., Artzy-Randrup, Y.A., Gimeno, L., Nieto, R., Cammeraat L.H. (2022) The Contribution of Transpiration to Precipitation Over African Watersheds. Water Resources Research, 58, e2021WR031721. https://doi. org/10.1029/2021WR031721

•	MEaSUREs vegetation continuous fields (VCF), Yearly, Global, 0.05 degree (https://cmr.earthdata.nasa.gov/search/concepts/C1452975608-LPDAAC_ECS.html; https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MCD12Q1#bands)
•	HydroSHEDS data is available via https://data.apps.fao.org/catalog/dataset/7707086d-af3c-41cc-8aa5-323d8609b2d1;
•	ERA-Interim data is available via https://apps.ecmwf.int/datasets/.
•	GLEAM data is available via https://www.gleam.eu/; 
•	MSWEP data is available via http://www.gloh2o.org/. 
•	OAFlux data is available from https://oaflux.whoi.edu/data-access/. 
•	LULC change data is available from https://doi.pangaea.de/10.1594/PANGAEA.921846 


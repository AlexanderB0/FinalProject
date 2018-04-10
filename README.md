# FinalProject

#Land Supply Analysis; Charlotte Lamb, Todd Doane, Alexander Bryant

# Import arcpy module
import arcpy

# Local variables:
TaxFC1 = "E:\\ComputerMapping\\ProjectGDB.gdb\\TaxFC1"
Parcel_TaxData__2_ = TaxFC1
Parcel_TaxData__3_ = Parcel_TaxData__2_
Parcel_TaxData__4_ = Parcel_TaxData__3_
Parcel_TaxData__5_ = Parcel_TaxData__4_
Parcel_TaxData__6_ = Parcel_TaxData__5_
Parcel_TaxData__7_ = Parcel_TaxData__6_
Parcel_TaxData__8_ = Parcel_TaxData__7_
TaxFC1__2_ = Parcel_TaxData__8_
Parcel_TaxData__10_ = TaxFC1__2_
Parcel_TaxData__12_ = Parcel_TaxData__10_
Parcel_TaxData__11_ = Parcel_TaxData__12_
TaxFC_Layer = "TaxFC1_Layer"
TaxFC_Layer__2_ = TaxFC_Layer
WetlandsAppend_shp = "E:\\Data\\Open Data Mecklenburg\\WetlandsAppend.shp"
Parcel_TaxData__32_ = TaxFC_Layer__2_
Parcel_TaxData__15_ = Parcel_TaxData__32_
FEMA_Floodway_shp = "E:\\Data\\Open Data Mecklenburg\\FEMA_Floodway.shp"
Parcel_TaxData__21_ = Parcel_TaxData__15_
Parcel_TaxData__17_ = Parcel_TaxData__21_
Historic_Cemeteries_shp = "E:\\Data\\Open Data Mecklenburg\\Historic_Cemeteries.shp"
Parcel_TaxData__16_ = Parcel_TaxData__17_
Parcel_TaxData__19_ = Parcel_TaxData__16_
ParkProperty_shp = "E:\\Data\\Open Data Mecklenburg\\ParkProperty.shp"
Parcel_TaxData__18_ = Parcel_TaxData__19_
Parcel_TaxData__20_ = Parcel_TaxData__18_
LYNXBlueLine_Station_shp = "E:\\Data\\Open Data Mecklenburg\\LYNXBlueLine_Station.shp"
LR_1_2_Buff_shp = "E:\\Data\\Created\\LR_1_2_Buff.shp"
Parcel_TaxData__23_ = Parcel_TaxData__20_
Parcel_TaxData__22_ = Parcel_TaxData__23_
LYNXBlueLine_Station_shp__2_ = "E:\\Data\\Open Data Mecklenburg\\LYNXBlueLine_Station.shp"
LR_1_4_Buff_shp = "E:\\Data\\Created\\LR_1_4_Buff.shp"
Parcel_TaxData__25_ = Parcel_TaxData__22_
Parcel_TaxData__24_ = Parcel_TaxData__25_
LandUse_Existing_shp = "E:\\Data\\Open Data Mecklenburg\\LandUse_Existing.shp"
LU_Vacant_shp = "E:\\Data\\Created\\LU_Vacant.shp"
Parcel_TaxData__27_ = Parcel_TaxData__24_
Parcel_TaxData__26_ = Parcel_TaxData__27_
LandUse_Existing_shp__2_ = "E:\\Data\\Open Data Mecklenburg\\LandUse_Existing.shp"
LU_Civic_Inst_shp = "E:\\Data\\Created\\LU_Civic_Inst.shp"
Parcel_TaxData__29_ = Parcel_TaxData__26_
Parcel_TaxData__30_ = Parcel_TaxData__29_
Parcel_TaxData__28_ = Parcel_TaxData__30_
Parcel_TaxData__31_ = Parcel_TaxData__28_
TaxFC_Layer__3_ = "TaxFC1_Layer"
TaxFC_Complete_V1 = "TaxFC_Complete_V1"

# Process: Add 'Wetland' Field
arcpy.AddField_management(TaxFC1, "wetland", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Floodplain' Field
arcpy.AddField_management(Parcel_TaxData__2_, "floodplain", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Lightrail' Field
arcpy.AddField_management(Parcel_TaxData__3_, "lightrail", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Vacant' Field
arcpy.AddField_management(Parcel_TaxData__4_, "Vacant", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Cemetery' Field
arcpy.AddField_management(Parcel_TaxData__5_, "cemetery", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Govt_Inst' Field
arcpy.AddField_management(Parcel_TaxData__6_, "govt_inst", "LONG", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Parks' Field
arcpy.AddField_management(Parcel_TaxData__7_, "Parks", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add Field
arcpy.AddField_management(Parcel_TaxData__8_, "valueratio", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'Exempt' Field
arcpy.AddField_management(TaxFC1__2_, "Exempt", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'RawScore' Field
arcpy.AddField_management(Parcel_TaxData__10_, "Raw_Score", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'DevClass' Field
arcpy.AddField_management(Parcel_TaxData__12_, "Dev_Class", "TEXT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Make Feature Layer
arcpy.MakeFeatureLayer_management(Parcel_TaxData__11_, TaxFC_Layer, "", "", "OBJECTID OBJECTID VISIBLE NONE;Shape Shape VISIBLE NONE;objectid_1 objectid_1 VISIBLE NONE;map_book map_book VISIBLE NONE;map_page map_page VISIBLE NONE;map_block map_block VISIBLE NONE;lot_num lot_num VISIBLE NONE;nc_pin nc_pin VISIBLE NONE;condo_town condo_town VISIBLE NONE;parcel_typ parcel_typ VISIBLE NONE;pid pid VISIBLE NONE;legal_from legal_from VISIBLE NONE;commonpid commonpid VISIBLE NONE;taxpid taxpid VISIBLE NONE;totalac totalac VISIBLE NONE;ownerlastn ownerlastn VISIBLE NONE;ownerfirst ownerfirst VISIBLE NONE;cownerfirs cownerfirs VISIBLE NONE;cownerlast cownerlast VISIBLE NONE;houseno houseno VISIBLE NONE;houseunit houseunit VISIBLE NONE;stdir stdir VISIBLE NONE;stname stname VISIBLE NONE;sttype sttype VISIBLE NONE;stsuffix stsuffix VISIBLE NONE;codemunici codemunici VISIBLE NONE;municipali municipali VISIBLE NONE;mailaddr1 mailaddr1 VISIBLE NONE;mailaddr2 mailaddr2 VISIBLE NONE;city city VISIBLE NONE;state state VISIBLE NONE;zipcode zipcode VISIBLE NONE;extravalue extravalue VISIBLE NONE;landvalue landvalue VISIBLE NONE;totalvalue totalvalue VISIBLE NONE;dateofsale dateofsale VISIBLE NONE;price price VISIBLE NONE;cardno cardno VISIBLE NONE;yearbuilt yearbuilt VISIBLE NONE;heatedarea heatedarea VISIBLE NONE;cdebuildin cdebuildin VISIBLE NONE;descbuildi descbuildi VISIBLE NONE;storyheigh storyheigh VISIBLE NONE;aheatingty aheatingty VISIBLE NONE;heatedfuel heatedfuel VISIBLE NONE;actype actype VISIBLE NONE;extwall extwall VISIBLE NONE;foundation foundation VISIBLE NONE;numfirepla numfirepla VISIBLE NONE;fireplaces fireplaces VISIBLE NONE;bldggrade bldggrade VISIBLE NONE;fullbaths fullbaths VISIBLE NONE;halfbaths halfbaths VISIBLE NONE;bedrooms bedrooms VISIBLE NONE;units units VISIBLE NONE;deedbook deedbook VISIBLE NONE;deedpage deedpage VISIBLE NONE;grantor grantor VISIBLE NONE;vacantorim vacantorim VISIBLE NONE;typeofdeed typeofdeed VISIBLE NONE;legalrefer legalrefer VISIBLE NONE;taxfire taxfire VISIBLE NONE;taxmun taxmun VISIBLE NONE;taxspecdis taxspecdis VISIBLE NONE;dateannexe dateannexe VISIBLE NONE;landusecod landusecod VISIBLE NONE;netbldgval netbldgval VISIBLE NONE;physicalde physicalde VISIBLE NONE;propertyus propertyus VISIBLE NONE;descproper descproper VISIBLE NONE;neighcode neighcode VISIBLE NONE;neighbourh neighbourh VISIBLE NONE;ownertype ownertype VISIBLE NONE;ownerno ownerno VISIBLE NONE;accounttyp accounttyp VISIBLE NONE;parlegalde parlegalde VISIBLE NONE;parlanduni parlanduni VISIBLE NONE;landsequen landsequen VISIBLE NONE;shape_Leng shape_Leng VISIBLE NONE;Shape_Length Shape_Length VISIBLE NONE;Shape_Area Shape_Area VISIBLE NONE;wetland wetland VISIBLE NONE;floodplain floodplain VISIBLE NONE;lightrail lightrail VISIBLE NONE;Vacant Vacant VISIBLE NONE;cemetery cemetery VISIBLE NONE;govt_inst govt_inst VISIBLE NONE;Parks Parks VISIBLE NONE;valueratio valueratio VISIBLE NONE;Exempt Exempt VISIBLE NONE;Raw_Score Raw_Score VISIBLE NONE;Dev_Class Dev_Class VISIBLE NONE")

# Process: Select Layer By Location
arcpy.SelectLayerByLocation_management(TaxFC_Layer, "INTERSECT", WetlandsAppend_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field
arcpy.CalculateField_management(TaxFC_Layer__2_, "wetland", "1", "PYTHON", "")

# Process: Select 'Floodplain' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__32_, "INTERSECT", FEMA_Floodway_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (2)
arcpy.CalculateField_management(Parcel_TaxData__15_, "floodplain", "1", "PYTHON", "")

# Process: Select 'Cemetery' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__21_, "INTERSECT", Historic_Cemeteries_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (3)
arcpy.CalculateField_management(Parcel_TaxData__17_, "cemetery", "1", "PYTHON", "")

# Process: Select 'Park' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__16_, "INTERSECT", ParkProperty_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (4)
arcpy.CalculateField_management(Parcel_TaxData__19_, "Parks", "1", "PYTHON", "")

# Process: Buffer
arcpy.Buffer_analysis(LYNXBlueLine_Station_shp, LR_1_2_Buff_shp, "0.5 Miles", "FULL", "ROUND", "NONE", "", "PLANAR")

# Process: Select '1/2 mile LR' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__18_, "INTERSECT", LR_1_2_Buff_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (5)
arcpy.CalculateField_management(Parcel_TaxData__20_, "lightrail", "3", "PYTHON", "")

# Process: Buffer (2)
arcpy.Buffer_analysis(LYNXBlueLine_Station_shp__2_, LR_1_4_Buff_shp, "0.25 Miles", "FULL", "ROUND", "NONE", "", "PLANAR")

# Process: Select '1/4 mile LR' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__23_, "INTERSECT", LR_1_4_Buff_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (6)
arcpy.CalculateField_management(Parcel_TaxData__22_, "lightrail", "5", "PYTHON", "")

# Process: Select
arcpy.Select_analysis(LandUse_Existing_shp, LU_Vacant_shp, "\"ExistingLU\" = 'Vacant'")

# Process: Select 'VacantLU' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__25_, "INTERSECT", LU_Vacant_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (7)
arcpy.CalculateField_management(Parcel_TaxData__24_, "Vacant", "5", "PYTHON", "")

# Process: Select (2)
arcpy.Select_analysis(LandUse_Existing_shp__2_, LU_Civic_Inst_shp, "\"ExistingLU\" =  'Civic/Institutional'")

# Process: Select 'Civic/Inst' By Location
arcpy.SelectLayerByLocation_management(Parcel_TaxData__27_, "INTERSECT", LU_Civic_Inst_shp, "", "NEW_SELECTION", "NOT_INVERT")

# Process: Calculate Field (8)
arcpy.CalculateField_management(Parcel_TaxData__26_, "govt_inst", "1", "PYTHON", "")

# Process: Calculate Field (9)
arcpy.CalculateField_management(Parcel_TaxData__29_, "ValueRatio", "!netbldgval!/ !landvalue!", "PYTHON", "")

# Process: Add 'RatioScore' Field
arcpy.AddField_management(Parcel_TaxData__30_, "ratioscore", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add 'AreaScore' Field 
arcpy.AddField_management(Parcel_TaxData__28_, "areascore", "FLOAT", "", "", "", "", "NULLABLE", "NON_REQUIRED", "")

# Process: Add Geometry Attributes
arcpy.AddGeometryAttributes_management(Parcel_TaxData__31_, "AREA", "FEET_US", "ACRES", "")

# Process: Make Feature Layer (2)
arcpy.MakeFeatureLayer_management(TaxFC_Layer__3_, TaxFC_Complete_V1, "", "", "OBJECTID OBJECTID VISIBLE NONE;Shape Shape VISIBLE NONE;objectid_1 objectid_1 VISIBLE NONE;map_book map_book VISIBLE NONE;map_page map_page VISIBLE NONE;map_block map_block VISIBLE NONE;lot_num lot_num VISIBLE NONE;nc_pin nc_pin VISIBLE NONE;condo_town condo_town VISIBLE NONE;parcel_typ parcel_typ VISIBLE NONE;pid pid VISIBLE NONE;legal_from legal_from VISIBLE NONE;commonpid commonpid VISIBLE NONE;taxpid taxpid VISIBLE NONE;totalac totalac VISIBLE NONE;ownerlastn ownerlastn VISIBLE NONE;ownerfirst ownerfirst VISIBLE NONE;cownerfirs cownerfirs VISIBLE NONE;cownerlast cownerlast VISIBLE NONE;houseno houseno VISIBLE NONE;houseunit houseunit VISIBLE NONE;stdir stdir VISIBLE NONE;stname stname VISIBLE NONE;sttype sttype VISIBLE NONE;stsuffix stsuffix VISIBLE NONE;codemunici codemunici VISIBLE NONE;municipali municipali VISIBLE NONE;mailaddr1 mailaddr1 VISIBLE NONE;mailaddr2 mailaddr2 VISIBLE NONE;city city VISIBLE NONE;state state VISIBLE NONE;zipcode zipcode VISIBLE NONE;extravalue extravalue VISIBLE NONE;landvalue landvalue VISIBLE NONE;totalvalue totalvalue VISIBLE NONE;dateofsale dateofsale VISIBLE NONE;price price VISIBLE NONE;cardno cardno VISIBLE NONE;yearbuilt yearbuilt VISIBLE NONE;heatedarea heatedarea VISIBLE NONE;cdebuildin cdebuildin VISIBLE NONE;descbuildi descbuildi VISIBLE NONE;storyheigh storyheigh VISIBLE NONE;aheatingty aheatingty VISIBLE NONE;heatedfuel heatedfuel VISIBLE NONE;actype actype VISIBLE NONE;extwall extwall VISIBLE NONE;foundation foundation VISIBLE NONE;numfirepla numfirepla VISIBLE NONE;fireplaces fireplaces VISIBLE NONE;bldggrade bldggrade VISIBLE NONE;fullbaths fullbaths VISIBLE NONE;halfbaths halfbaths VISIBLE NONE;bedrooms bedrooms VISIBLE NONE;units units VISIBLE NONE;deedbook deedbook VISIBLE NONE;deedpage deedpage VISIBLE NONE;grantor grantor VISIBLE NONE;vacantorim vacantorim VISIBLE NONE;typeofdeed typeofdeed VISIBLE NONE;legalrefer legalrefer VISIBLE NONE;taxfire taxfire VISIBLE NONE;taxmun taxmun VISIBLE NONE;taxspecdis taxspecdis VISIBLE NONE;dateannexe dateannexe VISIBLE NONE;landusecod landusecod VISIBLE NONE;netbldgval netbldgval VISIBLE NONE;physicalde physicalde VISIBLE NONE;propertyus propertyus VISIBLE NONE;descproper descproper VISIBLE NONE;neighcode neighcode VISIBLE NONE;neighbourh neighbourh VISIBLE NONE;ownertype ownertype VISIBLE NONE;ownerno ownerno VISIBLE NONE;accounttyp accounttyp VISIBLE NONE;parlegalde parlegalde VISIBLE NONE;parlanduni parlanduni VISIBLE NONE;landsequen landsequen VISIBLE NONE;shape_Leng shape_Leng VISIBLE NONE;Shape_Length Shape_Length VISIBLE NONE;Shape_Area Shape_Area VISIBLE NONE;wetland wetland VISIBLE NONE;floodplain floodplain VISIBLE NONE;lightrail lightrail VISIBLE NONE;Vacant Vacant VISIBLE NONE;cemetery cemetery VISIBLE NONE;govt_inst govt_inst VISIBLE NONE;Parks Parks VISIBLE NONE;valueratio valueratio VISIBLE NONE;Exempt Exempt VISIBLE NONE;Raw_Score Raw_Score VISIBLE NONE;Dev_Class Dev_Class VISIBLE NONE;ratioscore ratioscore VISIBLE NONE;areascore areascore VISIBLE NONE;POLY_AREA POLY_AREA VISIBLE NONE")



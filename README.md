# ETL_Bulk_CSV_Upload
Bulk CSV file upload into Data warehouse
How to take N number of CSV or Excel file and upload the in destination DB. We have created couple of notepad and insert the data as csv format.At first We have to create 
a blank table in destination DB where we can insert the data from source, but in this table we have created some extra column like Discount Amount, USD Amount, Discount
Percentage,Customer Type etc. We have Id,Customername,Product Name,Product Quantity,Product Price,Purchase Date. In the dataflow we took a flat file source and chose one csv file then
took a data convertion task to convert the data type in respected columns. After that took a derived column to change the customer name into upper case and create a USD
Amount column. Then used conditional column to create customer type and seprated them as condition wise. After that we have to used once again derived column in order to 
mention the discount for different type of customer type. Then used union all task to union all the columns and then took ADO NET DESTINATION to upload the data in 
destination table. So we have done with data extration,transformation and load. But I have chose only one csv file but we have four csv files, in order to make it dynamic 
we have to create variable and foreach loop container, in foreach loop container we need to change the enumerator to foreach file enumerator and give the file location  
also put the variable in variable maping. We need to put the variable in connection manager expressions. Now we want to truncate the table each and every time when ever 
we run this package so, for that we picked execute task and use truncate command. Now we edit the breakpoint to each event point so we can watch it and add the variable
in watch point so we can continue to complete every event. 

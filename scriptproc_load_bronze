 

CREATE OR ALTER PROCEDURE bronze.load_bronze AS
BEGIN

    DECLARE @start_time DATETIME, @endtime DATETIME;

    BEGIN TRY

        PRINT '====================';
        PRINT 'loading bronze layer';
        PRINT '====================';

        PRINT ' ----------------------------------';
        PRINT 'loading crm tables';
        PRINT ' ----------------------------------';

        SET @start_time = GETDATE();

        PRINT '>> Truncating table: bronze.crm_cust_info';

        TRUNCATE TABLE bronze.crm_cust_info;

        PRINT '>>Inserting Data Into :  bronze.crm_cust_info';

        BULK INSERT bronze.crm_cust_info
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_crm\cust_info.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';


        PRINT ' ----------------------------------';
        PRINT 'loading crm tables';
        PRINT ' ----------------------------------';

        SET @start_time = GETDATE();

        PRINT '>> Truncating table:bronze.crm_prd_info';

        TRUNCATE TABLE bronze.crm_prd_info;

        PRINT '>>Inserting Data Into : bronze.crm_prd_info';

        BULK INSERT bronze.crm_prd_info
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_crm\prd_info.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';


        SET @start_time = GETDATE();

        PRINT ' ----------------------------------';
        PRINT 'loading crm tables';
        PRINT ' ----------------------------------';

        PRINT '>> Truncating table:bronze.crm_SALES_DETAILS';

        TRUNCATE TABLE bronze.crm_SALES_DETAILS;

        PRINT '>>Inserting Data Into : bronze.crm_sales_details';

        BULK INSERT bronze.crm_sales_details
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_crm\sales_details.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';


        SET @start_time = GETDATE();

        PRINT ' ----------------------------------';
        PRINT 'loading erp tables';
        PRINT ' ----------------------------------';

        PRINT '>> Truncating table: bronze.erp_cust_az12';

        TRUNCATE TABLE bronze.erp_cust_az12;

        PRINT '>>Inserting Data Into :bronze.erp_cust_az12';

        BULK INSERT bronze.erp_cust_az12
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_erp\CUST_AZ12.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';


        SET @start_time = GETDATE();

        PRINT ' ----------------------------------';
        PRINT 'loading erp tables';
        PRINT ' ----------------------------------';

        PRINT '>> Truncating table:bronze.erp_loc_a101';

        TRUNCATE TABLE bronze.erp_loc_a101;

        PRINT '>>Inserting Data Into :bronze.erp_loc_a101';

        BULK INSERT bronze.erp_loc_a101
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_erp\LOC_A101.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';


        SET @start_time = GETDATE();

        PRINT ' ----------------------------------';
        PRINT 'loading erp tables';
        PRINT ' ----------------------------------';

        PRINT '>> Truncating table:bronze.erp_PX_CAT_G1V2';

        TRUNCATE TABLE bronze.erp_PX_CAT_G1V2;

        PRINT '>>Inserting Data Into :bronze.erp_PX_CAT_G1V2';

        BULK INSERT bronze.erp_PX_CAT_G1V2
        FROM 'E:\DATA ANALYST\SQL\SQL YOUTUBE COURSE BY BRA\Project\sql-data-warehouse-project-main\datasets\source_erp\PX_CAT_G1V2.csv'
        WITH (
            FIRSTROW = 2,
            FIELDTERMINATOR = ',',
            TABLOCK
        );

        SET @endtime = GETDATE();

        PRINT '>> Load duration: ' 
            + CAST(DATEDIFF(SECOND, @start_time, @endtime) AS NVARCHAR) 
            + ' seconds';

        PRINT '>>-----------------------';

    END TRY

    BEGIN CATCH

        PRINT '==============================';
        PRINT 'Error occurred during loading Bronze layer';
        PRINT 'Error Message: ' + ERROR_MESSAGE();
        PRINT 'Error Number: ' + CAST(ERROR_NUMBER() AS NVARCHAR);
        PRINT '==============================';


    END CATCH

END;
GO

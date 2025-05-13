# Manual mapping feature

Manual mapping feature handles user manual anotations through excel files to cpi_prod_dim table

##### Jobs
- mapping_export_job
  - extracts partitioned data into excel spreadsheets 
- mapping_import_job
  - processes annotated files from user input folder
  - updates cpi_prod_dim_table with data extracted from users

##### Folder structure
```txt

kondo
 |----manual_mapping
       |----mapping_export_job
            |-export_job.py  # when job = notebook
       |----mapping_import_job
            |----tasks # when job = pipeline of notebooks
                  |-task1_task.py
                  |-task2_task.py
                  |-task3_task.py
```

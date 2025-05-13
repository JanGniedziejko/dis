# Manual mapping feature

Manual mapping feature handles user manual anotations through excel files to cpi_prod_dim table

##### Jobs
- mapping_export_job (weekly or manually trigerred)
  - extracts partitioned data to Sharepoint as excel spreadsheets for users
  - Format the excels (locking cells, set allowed values, etc.)
- mapping_import_job 
  - processes annotated files from user input folder
  - updates cpi_prod_dim_table with data extracted from users

##### Folder structure
```txt

kondo/
└── manual_mapping/
    ├── mapping_export_job/
    │   ├──
    │   └── 
    │
    ├── mapping_import_job/
    │   └── tasks
    │       ├── 1_detect_files_task.py
    │       ├── 2_excel_files_detected.py
    │       ├── 3_validate_excel_file_task.py
    │       ├── 4_1_apply_accepted_records.py
    │       ├── 4_2_handle_rejected_records.py
    │       └── 5_move_processed_files.py
    │
    └── README.md  # documentation
```

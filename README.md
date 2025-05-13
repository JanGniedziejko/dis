# Manual mapping feature

Manual mapping feature handles user manual anotations through excel files to cpi_prod_dim table

---
### Jobs
#### - mapping_export_job (weekly or manually trigerred)
  - extracts partitioned data into formatted excel spreadsheets ()
  - put the excel files into '/{sub_sector}/New/' directory in pgone Sharepoint
 
#### - mapping_import_job (trigerred frequently everyday)
  - detect freshly annotated files from user input folder
    - check the file structure:
      - label records into processed/rejected with the reason of rejection
        - for processed records:
          - update cpi_prod_dim_table with data extracted from users
          - move the excel file to '/{sub_sector}/Processed/' directory
        - for rejected records:
          - create a new excel file in '/{sub_sector}/Rejected/' directory
    

---
### Folder structure
```txt

kondo/
└── manual_mapping/
    ├── mapping_export_job/
    │   ├── export_job.py
    │   └── styling_excel.py 
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

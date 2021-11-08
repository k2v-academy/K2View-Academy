# Get Task Execution Reports APIs

## Get Task Execution Summary Report 

### API URL

/taskSummaryReport/{executionId}/luName/{luName}

### HTTP Method

POST

### API Category

TDM_Tasks

### API Description

Gets the task summary report.

### API Input

- executionId
- luName - populate this parameter by 'ALL' to get a summary execution report on the execution. This report includes all the related task's LUs.

#### API Input Example

```
http://localhost:3213/api/taskSummaryReport/490/luName/ALL
```

### API Output Examples

```json
{
   "result":{
      "General Info":[
         {
            "task_name":"loadVIPCus",
            "task_id":3,
            "task_execution_id":"6",
            "created_by":"admin",
            "executed_by":"joe",
            "start_execution":"2021-11-07 15:52:09.0",
            "end_execution":"2021-11-07 15:52:30.0",
            "execution_status":"completed",
            "source_env":"SRC",
            "target_env":"TAR",
            "be_name":"Customer",
            "task_type":"LOAD",
            "selection_method":"Parameters",
            "task_sync_mode":null,
            "env_sync_mode":"ON",
            "operation_mode":"Delete and load entity",
            "replace_sequences":"false",
            "version_ind":"false",
            "selected_version_task_name":null,
            "selected_version_datetime":null,
            "selected_ref_version_task_name":null,
            "selected_ref_version_datetime":null,
            "scheduling_parameters":"immediate",
            "schedule_expiration_date":null,
            "override_parameters":"{\"NO_OF_ENTITIES\":6}"
         }
      ],
      "Task Execution Summary":[
         {
            "LUs":{
               "LU Load Summary":[
                  {
                     "lu_name":"Customer",
                     "fabric_execution_id":"71175bf8-e606-49a9-b5e9-489b99c3fa46",
                     "parent_lu_name":"null",
                     "data_center_name":"DC1",
                     "start_execution_time":"2021-11-07 15:52:09.0",
                     "end_execution_time":"2021-11-07 15:52:10.0",
                     "num_of_processed_entities":6,
                     "num_of_copied_entities":6,
                     "num_of_failed_entities":0,
                     "num_of_processed_ref_tables":0,
                     "num_of_copied_ref_tables":0,
                     "num_of_failed_ref_tables":0
                  }
               ]
            }
         },
         {
            "LUs":{
               "LU Load Summary":[
                  {
                     "lu_name":"Collection",
                     "fabric_execution_id":"d522f580-ff91-4835-a35d-e6fe9dc75685",
                     "parent_lu_name":"Customer",
                     "data_center_name":"DC1",
                     "start_execution_time":"2021-11-07 15:52:29.0",
                     "end_execution_time":"2021-11-07 15:52:30.0",
                     "num_of_processed_entities":2,
                     "num_of_copied_entities":2,
                     "num_of_failed_entities":0,
                     "num_of_processed_ref_tables":0,
                     "num_of_copied_ref_tables":0,
                     "num_of_failed_ref_tables":0
                  }
               ]
            }
         },
         {
            "LUs":{
               "LU Load Summary":[
                  {
                     "lu_name":"Billing",
                     "fabric_execution_id":"3dbf3bb7-075e-4eea-a151-f257b3ee6874",
                     "parent_lu_name":"Customer",
                     "data_center_name":"null",
                     "start_execution_time":"2021-11-07 15:52:29.0",
                     "end_execution_time":"2021-11-07 15:52:30.0",
                     "num_of_processed_entities":18,
                     "num_of_copied_entities":1,
                     "num_of_failed_entities":17,
                     "num_of_processed_ref_tables":0,
                     "num_of_copied_ref_tables":0,
                     "num_of_failed_ref_tables":0
                  }
               ]
            }
         },
         {
            "LUs":{
               "LU Load Summary":[
                  {
                     "lu_name":"Orders",
                     "fabric_execution_id":"d4033252-e1b0-4267-bb2d-46ff7795c250",
                     "parent_lu_name":"Customer",
                     "data_center_name":"null",
                     "start_execution_time":"2021-11-07 15:52:29.0",
                     "end_execution_time":"2021-11-07 15:52:30.0",
                     "num_of_processed_entities":18,
                     "num_of_copied_entities":18,
                     "num_of_failed_entities":0,
                     "num_of_processed_ref_tables":0,
                     "num_of_copied_ref_tables":0,
                     "num_of_failed_ref_tables":0
                  }
               ]
            }
         }
      ],
      "List of Root Entities":{
         "Number of Copied Entities":[
            {
               "number_of_copied_root_entities":0
            }
         ],
         "List of Copied Entities":[
            {
               "source_id":"SRC_1016",
               "target_id":"1016"
            },
            {
               "source_id":"SRC_329",
               "target_id":"329"
            },
            {
               "source_id":"SRC_360",
               "target_id":"360"
            },
            {
               "source_id":"SRC_448",
               "target_id":"448"
            },
            {
               "source_id":"SRC_663",
               "target_id":"663"
            },
            {
               "source_id":"SRC_679",
               "target_id":"679"
            }
         ],
         "Number of Failed Entities":[
            {
               "number_of_failed_root_entities":0
            }
         ],
         "List of Failed Entities":[
            
         ]
      },
      "List of Reference Tables":{
         "Number of Copied Reference Tables":[
            {
               "count":0
            }
         ],
         "List of Copied Reference Tables":[
            
         ],
         "Number of Failed Reference Tables":[
            {
               "count":0
            }
         ],
         "List of Failed Reference Tables":[
            
         ]
      },
      "Error Summary":[
         {
            "lu_name":"Billing",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "number_of_entities":17,
            "number_of_records":17
         },
         {
            "lu_name":"Billing",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "number_of_entities":17,
            "number_of_records":17
         }
      ],
      "Error Details":[
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1125",
            "target_entity_id":"1125",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"5592,2815,2015-04-06 14:39:22,3,24.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1125",
            "target_entity_id":"1125",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1126",
            "target_entity_id":"1126",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1126",
            "target_entity_id":"1126",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"5593,2816,2016-02-27 04:30:58,1,820.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1127",
            "target_entity_id":"1127",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1127",
            "target_entity_id":"1127",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"5600,2820,2016-09-13 08:01:49,2,144.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1128",
            "target_entity_id":"1128",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1128",
            "target_entity_id":"1128",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"5602,2821,2017-02-11 17:56:25,1,273.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1629",
            "target_entity_id":"1629",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"8151,4092,2017-01-03 01:10:57,3,436.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1629",
            "target_entity_id":"1629",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1630",
            "target_entity_id":"1630",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1630",
            "target_entity_id":"1630",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"8153,4094,2016-01-03 00:48:11,1,511.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1631",
            "target_entity_id":"1631",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1631",
            "target_entity_id":"1631",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"8160,4098,2016-09-15 01:06:15,1,172.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1679",
            "target_entity_id":"1679",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_1679",
            "target_entity_id":"1679",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"8364,4181,2015-03-21 14:09:26,1,1000.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_2507",
            "target_entity_id":"2507",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"12502,6238,2016-10-11 16:37:16,1,797.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_2507",
            "target_entity_id":"2507",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_2508",
            "target_entity_id":"2508",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"12512,6245,2015-03-11 23:11:00,3,553.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_2508",
            "target_entity_id":"2508",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_834",
            "target_entity_id":"834",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4139,2056,2016-08-30 14:49:04,1,36.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_834",
            "target_entity_id":"834",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_835",
            "target_entity_id":"835",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4149,2062,2017-01-30 17:59:53,3,48.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_835",
            "target_entity_id":"835",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_836",
            "target_entity_id":"836",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_836",
            "target_entity_id":"836",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4155,2064,2015-12-04 04:44:41,2,933.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_905",
            "target_entity_id":"905",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_905",
            "target_entity_id":"905",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4521,2257,2015-09-18 03:07:18,1,755.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_906",
            "target_entity_id":"906",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_906",
            "target_entity_id":"906",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4526,2259,2015-07-26 16:11:30,1,895.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_907",
            "target_entity_id":"907",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_907",
            "target_entity_id":"907",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4533,2261,2015-09-26 14:57:05,2,424.0,\n"
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_908",
            "target_entity_id":"908",
            "flow_name":"TDMOrchestrator",
            "stage_name":"Load Tables",
            "actor_name":"Load All Tables",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"Flow: LoadAllTables Level: 4 Stage: Load Tables Level 3 Actor: load_PAYMENT Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70 Cause: ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) InnerFlowException: Flow: load_PAYMENT Level: 8 Stage: Set payment method Actor: Load PAYMENT - DEV ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?) class org.postgresql.util.PSQLException Cause: ERROR: column \"payment_method\" of relation \"payment\" does not exist\n  Position: 70",
            "actor_parameters":""
         },
         {
            "lu_name":"Billing",
            "source_entity_id":"SRC_908",
            "target_entity_id":"908",
            "flow_name":"load_PAYMENT",
            "stage_name":"Set payment method",
            "actor_name":"Load PAYMENT - DEV",
            "error_category":"Entity Failed",
            "error_code":"0",
            "error_message":"ERROR: current transaction is aborted, commands ignored until end of transaction block\nINSERT INTO PAYMENT (INVOICE_ID,PAYMENT_ID,ISSUED_DATE,STATUS,AMOUNT,PAYMENT_METHOD) VALUES (?,?,?,?,?,?)",
            "actor_parameters":"4539,2263,2015-04-09 22:11:19,1,246.0,\n"
         }
      ],
      "Statistics Report":[
         {
            "lu_name":"Customer",
            "table_name":"CASE_NOTE",
            "target_count":"52",
            "source_count":"52",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Customer",
            "table_name":"ACTIVITY",
            "target_count":"34",
            "source_count":"34",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Customer",
            "table_name":"CASES",
            "target_count":"17",
            "source_count":"17",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Customer",
            "table_name":"ADDRESS",
            "target_count":"6",
            "source_count":"6",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Customer",
            "table_name":"CONTRACT",
            "target_count":"18",
            "source_count":"18",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Customer",
            "table_name":"CUSTOMER",
            "target_count":"6",
            "source_count":"6",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Collection",
            "table_name":"COLLECTION",
            "target_count":"2",
            "source_count":"2",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Billing",
            "table_name":"SUBSCRIBER",
            "target_count":"18",
            "source_count":"18",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Orders",
            "table_name":"ORDERS",
            "target_count":"18",
            "source_count":"18",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Billing",
            "table_name":"INVOICE",
            "target_count":"102",
            "source_count":"102",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Billing",
            "table_name":"OFFER",
            "target_count":"9",
            "source_count":"9",
            "diff":"0",
            "results":"OK"
         },
         {
            "lu_name":"Billing",
            "table_name":"BALANCE",
            "target_count":"170",
            "source_count":"170",
            "diff":"0",
            "results":"OK"
         }
      ],
      "Replace Sequence Summary Report":[
         
      ]
   },
   "errorCode":"SUCCESS",
   "message":""
}
```



```json
{
  "result": {
    "General Info": [
      {
        "task_name": "createTaskByTester",
        "task_id": 294,
        "task_execution_id": "490",
        "created_by": "tali",
        "executed_by": "admin",
        "start_execution": "2021-06-16 16:24:21.0",
        "end_execution": "2021-06-16 16:24:32.0",
        "execution_status": "completed",
        "source_env": "SRC",
        "target_env": "TAR",
        "be_name": "CUSTOMER",
        "task_type": "LOAD",
        "selection_method": "Randon Selection",
        "task_sync_mode": null,
        "env_sync_mode": "ON",
        "operation_mode": "Delete and load entity",
        "replace_sequences": "false",
        "version_ind": "false",
        "selected_version_task_name": null,
        "selected_version_datetime": null,
        "selected_ref_version_task_name": null,
        "selected_ref_version_datetime": null,
        "scheduling_parameters": "immediate",
        "schedule_expiration_date": null,
        "override_parameters": null
      }
    ],
    "Task Execution Summary": [
      {
        "lu_name": "Customer",
        "fabric_execution_id": "aced32c8-7d2c-43cd-a7ba-f363733f59e7",
        "parent_lu_name": "null",
        "data_center_name": "null",
        "start_execution_time": "2021-06-16 16:24:21.0",
        "end_execution_time": "2021-06-16 16:24:22.0",
        "num_of_processed_entities": 5,
        "num_of_copied_entities": 5,
        "num_of_failed_entities": 0,
        "num_of_processed_ref_tables": 0,
        "num_of_copied_ref_tables": 0,
        "num_of_failed_ref_tables": 0
      },
      {
        "lu_name": "Collection",
        "fabric_execution_id": "4f4e3609-1b9b-418b-b059-ceb38b4e93eb",
        "parent_lu_name": "Customer",
        "data_center_name": "null",
        "start_execution_time": "2021-06-16 16:24:31.0",
        "end_execution_time": "2021-06-16 16:24:32.0",
        "num_of_processed_entities": 3,
        "num_of_copied_entities": 3,
        "num_of_failed_entities": 0,
        "num_of_processed_ref_tables": 0,
        "num_of_copied_ref_tables": 0,
        "num_of_failed_ref_tables": 0
      },
      {
        "lu_name": "Billing",
        "fabric_execution_id": "8868047e-0aa4-4793-a2f2-d41f8a24a94b",
        "parent_lu_name": "Customer",
        "data_center_name": "null",
        "start_execution_time": "2021-06-16 16:24:31.0",
        "end_execution_time": "2021-06-16 16:24:32.0",
        "num_of_processed_entities": 17,
        "num_of_copied_entities": 17,
        "num_of_failed_entities": 0,
        "num_of_processed_ref_tables": 0,
        "num_of_copied_ref_tables": 0,
        "num_of_failed_ref_tables": 0
      },
      {
        "lu_name": "Orders",
        "fabric_execution_id": "d423dcfc-e175-4aed-b31f-0ca55e59f095",
        "parent_lu_name": "Customer",
        "data_center_name": "null",
        "start_execution_time": "2021-06-16 16:24:31.0",
        "end_execution_time": "2021-06-16 16:24:32.0",
        "num_of_processed_entities": 27,
        "num_of_copied_entities": 27,
        "num_of_failed_entities": 0,
        "num_of_processed_ref_tables": 0,
        "num_of_copied_ref_tables": 0,
        "num_of_failed_ref_tables": 0
      }
    ],
    "List of Root Entities": {
      "Number of Copied Entities": [
        {
          "number_of_copied_root_entities": 5
        }
      ],
      "List of Copied Entities": [
        {
          "source_id": "SRC_36",
          "target_id": "36"
        },
        {
          "source_id": "SRC_532",
          "target_id": "532"
        },
        {
          "source_id": "SRC_577",
          "target_id": "577"
        },
        {
          "source_id": "SRC_627",
          "target_id": "627"
        },
        {
          "source_id": "SRC_794",
          "target_id": "794"
        }
      ],
      "Number of Failed Entities": [
        {
          "number_of_failed_root_entities": 0
        }
      ],
      "List of Failed Entities": []
    },
    "List of Reference Tables": {
      "Number of Copied Reference Tables": [
        {
          "count": 0
        }
      ],
      "List of Copied Reference Tables": [],
      "Number of Failed Reference Tables": [
        {
          "count": 0
        }
      ],
      "List of Failed Reference Tables": []
    },
    "Error Summary": [],
    "Error Details": [],
    "Statistics Report": [
      {
        "lu_name": "Billing",
        "table_name": "BALANCE",
        "target_count": "172",
        "source_count": "172",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "INVOICE",
        "target_count": "107",
        "source_count": "107",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "OFFER",
        "target_count": "9",
        "source_count": "9",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "SUBSCRIBER",
        "target_count": "17",
        "source_count": "17",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Collection",
        "table_name": "COLLECTION",
        "target_count": "3",
        "source_count": "3",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "ACTIVITY",
        "target_count": "26",
        "source_count": "26",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "ADDRESS",
        "target_count": "5",
        "source_count": "5",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "CASE_NOTE",
        "target_count": "35",
        "source_count": "35",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "CASES",
        "target_count": "16",
        "source_count": "16",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "CONTRACT",
        "target_count": "17",
        "source_count": "17",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Customer",
        "table_name": "CUSTOMER",
        "target_count": "5",
        "source_count": "5",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Orders",
        "table_name": "ORDERS",
        "target_count": "27",
        "source_count": "27",
        "diff": "0",
        "results": "OK"
      }
    ],
    "Replace Sequence Summary Report": []
  },
  "errorCode": "SUCCESS",
  "message": ""
}
```



## Load Tasks - Get a Summary Execution Report on a Given LU

### API URL

/taskSummaryReport/{executionId}/luName/{luName}

### HTTP Method

POST

### API Category

TDM_Tasks

### API Description

Gets the task summary report on a given LU.

### API Input

- executionId
- luName - populate this parameter by the LU name.

#### API Input Example

```
http://localhost:3213/api/taskSummaryReport/490/luName/Billing
```

### API Output Example

```json
{
  "result": {
    "General Info": [
      {
        "task_name": "createTaskByTester",
        "task_id": 294,
        "task_execution_id": "490",
        "created_by": "tali",
        "executed_by": "admin",
        "start_execution": "2021-06-16 16:24:21.0",
        "end_execution": "2021-06-16 16:24:32.0",
        "execution_status": "completed",
        "source_env": "SRC",
        "target_env": "TAR",
        "be_name": "CUSTOMER",
        "task_type": "LOAD",
        "selection_method": "Randon Selection",
       	"task_sync_mode": null,
        "env_sync_mode": "ON",
        "operation_mode": "Delete and load entity",
        "replace_sequences": "false",
        "version_ind": "false",
        "selected_version_task_name": null,
        "selected_version_datetime": null,
        "selected_ref_version_task_name": null,
        "selected_ref_version_datetime": null,
        "scheduling_parameters": "immediate",
        "schedule_expiration_date": null,
        "override_parameters": null
      }
    ],
    "Task Execution Summary": [
      {
        "lu_name": "Billing",
        "fabric_execution_id": "8868047e-0aa4-4793-a2f2-d41f8a24a94b",
        "parent_lu_name": "Customer",
        "data_center_name": "null",
        "start_execution_time": "2021-06-16 16:24:31.0",
        "end_execution_time": "2021-06-16 16:24:32.0",
        "num_of_processed_entities": 17,
        "num_of_copied_entities": 17,
        "num_of_failed_entities": 0,
        "num_of_processed_ref_tables": 0,
        "num_of_copied_ref_tables": 0,
        "num_of_failed_ref_tables": 0
      }
    ],
    "List of Root Entities": {
      "Number of Copied Entities": [
        {
          "number_of_copied_root_entities": 17
        }
      ],
      "List of Copied Entities": [
        {
          "source_id": "SRC_102",
          "target_id": "102"
        },
        {
          "source_id": "SRC_103",
          "target_id": "103"
        },
        {
          "source_id": "SRC_104",
          "target_id": "104"
        },
        {
          "source_id": "SRC_105",
          "target_id": "105"
        },
        {
          "source_id": "SRC_106",
          "target_id": "106"
        },
        {
          "source_id": "SRC_1324",
          "target_id": "1324"
        },
        {
          "source_id": "SRC_1325",
          "target_id": "1325"
        },
        {
          "source_id": "SRC_1326",
          "target_id": "1326"
        },
        {
          "source_id": "SRC_1429",
          "target_id": "1429"
        },
        {
          "source_id": "SRC_1430",
          "target_id": "1430"
        },
        {
          "source_id": "SRC_1431",
          "target_id": "1431"
        },
        {
          "source_id": "SRC_1432",
          "target_id": "1432"
        },
        {
          "source_id": "SRC_1537",
          "target_id": "1537"
        },
        {
          "source_id": "SRC_1538",
          "target_id": "1538"
        },
        {
          "source_id": "SRC_1965",
          "target_id": "1965"
        },
        {
          "source_id": "SRC_1966",
          "target_id": "1966"
        },
        {
          "source_id": "SRC_1967",
          "target_id": "1967"
        }
      ],
      "Number of Failed Entities": [
        {
          "number_of_failed_root_entities": 0
        }
      ],
      "List of Failed Entities": []
    },
    "List of Reference Tables": {
      "Number of Copied Reference Tables": [
        {
          "count": 0
        }
      ],
      "List of Copied Reference Tables": [],
      "Number of Failed Reference Tables": [
        {
          "count": 0
        }
      ],
      "List of Failed Reference Tables": []
    },
    "Error Summary": [],
    "Error Details": [],
    "Statistics Report": [
      {
        "lu_name": "Billing",
        "table_name": "BALANCE",
        "target_count": "172",
        "source_count": "172",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "INVOICE",
        "target_count": "107",
        "source_count": "107",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "OFFER",
        "target_count": "9",
        "source_count": "9",
        "diff": "0",
        "results": "OK"
      },
      {
        "lu_name": "Billing",
        "table_name": "SUBSCRIBER",
        "target_count": "17",
        "source_count": "17",
        "diff": "0",
        "results": "OK"
      }
    ],
    "Replace Sequence Summary Report": []
  },
  "message": ""
}
```



## Extract Tasks - Get Execution Reports on a Given LU

### API URL

/migrateStatusWs

### HTTP Method

POST

### API Category

TDM_Tasks

### API Description

Gets a summary of detailed information of the input batch IDs (LU execution). This API gets the run mode and a list of batch IDs or only one batch id as input values.
The API's run mode can have the following values:

- 'D': detailed execution. Returns detailed information of all entities and their execution status.

- 'S': summary information of the execution

- 'H': get the batch command.



### API Input

```
{
  "migrateIds": {},
  "runModes": [
    "string"
  ]
}
```

**Note:**

The **migrateIds** parameter is populated by the batch IDs related to the task execution. The batch ID is populated in the **fabric_execution_id** attribute of **/task/{taskExeId}/history** API's output.

#### API Input Examples

##### Get a Summary Report

```json
{"migrateIds": "3e8e8e44-9c97-4921-a622-f29161a8a112", "runModes": ["S", "H"]}
```



##### Get Summary and Detailed Reports with the Entity List and their Execution Status

```json
{"migrateIds": "3e8e8e44-9c97-4921-a622-f29161a8a112", "runModes": ["D", "H", "S"]}
```


 [![Previous](/articles/images/Previous.png)](01_tdm_basic_task_execution_flow.md)

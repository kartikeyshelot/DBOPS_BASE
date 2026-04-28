{
  "sqlStatement": "SELECT lineItem_UsageAccountId AS \"Account_ID\", product_region AS \"Region\", lineItem_ResourceId AS \"Instance_ID\", product_instanceType AS \"Instance_Type\", product_databaseEngine AS \"Database_Engine\", product_databaseEdition AS \"Database_Edition\", product_vcpu AS \"vCPU\", lineItem_UsageType AS \"Usage_Type\", SUM(lineItem_UnblendedCost) AS \"Total_Cost\" FROM AWS_CUR WHERE lineItem_UsageType LIKE '%ExtendedSupport%' AND lineItem_LineItemType = 'Usage' GROUP BY lineItem_UsageAccountId, product_region, lineItem_ResourceId, product_instanceType, product_databaseEngine, product_databaseEdition, product_vcpu, lineItem_UsageType ORDER BY \"Total_Cost\" DESC",
  "needBackLinkingForTags": true,
  "dataGranularity": "MONTHLY",
  "timeRange": {
    "last": 3
  },
  "limit": -1
}

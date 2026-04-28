SELECT
    line_item_resource_id,
    product_database_engine,
    product_engine_version,
    product_vcpu,
    line_item_usage_type,
    SUM(line_item_unblended_cost) AS total_cost
FROM
    aws_cost_and_usage
WHERE
    line_item_usage_type LIKE '%ExtendedSupport%'
    AND line_item_line_item_type = 'Usage'
GROUP BY
    line_item_resource_id,
    product_database_engine,
    product_engine_version,
    product_vcpu,
    line_item_usage_type
ORDER BY
    total_cost DESC;

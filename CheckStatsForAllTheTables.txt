SELECT t.name TableName, s.[name] StatName, STATS_DATE(t.object_id,s.[stats_id]) LastUpdated 
FROM sys.[stats] AS s
JOIN sys.[tables] AS t
    ON [s].[object_id] = [t].[object_id]
WHERE t.type = 'u'

Query Audit locateDevice actions
	IntuneAuditLogs 
	| where OperationName contains "locateDevice"
	  and ResultType == 'Success'

Function AuditIntuneLocateDevice

![[Create Alert Rule.gif]]
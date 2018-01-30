#Problemas de conexión en SAP B1 "You are not connected to a company"

1. Ingresa a la configuración del COM SAP.
2. Valida que la conexión del COM es liberada antes de volver a generar una nueva conexión. (En ocasiones sap cuelga las conexiones y no se cierran, es necesario cerrar todo antes de volver abrir una nueva).
3. En ocasiones el language del com debe ser igual al de sap. Ya que determina el language en sql server que genera problemas de conexión.
4. Verifica la configuración y nombre del servidor de licencias. En ocasiones el tener el mismo nombre en las licencias produce un problema, ya que sap valida la conexion por el nombre del servidor. Igual sucede que se cambio el nombre del servidor y sap no puede encontrar el servidor.
5. Los accesos de sql server al realizar backup o rollback de sistema fallan, pueden provocar problemas en la conexión del sql server, revisa los accesos de sql server si presentan algun problema de permisos.
6. Validar el nombre de la base de datos en sql server o si la base de datos presenta algun problema.
7. Validar si los accesos de usuario de sap fueron modificados, lo que provoca problemas de conexión en sap.
8. Al realizar actualizaciones de sistema sobre SAP B1 provoca que sea necesario actualizar igual el COM que se encarga de la conexión. Debido a que cada version nueva de sap solicita actualizar sql server. Por lo cual la configuración de sql server cambio. En caso que haya cambiado, agregar la configuración de sql server:

oCom.DbServerType = SAPbobsCOM.BoDataServerTypes.dst_MSSQL2016;

El nuevo com indica la version mas reciente de sql server que se permite. Por lo cual es necesario actualizar.


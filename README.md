### Documentation is included in the Documentation folder ###


### REFrameWork Template ###
**Robotic Enterprise Framework**

* Built on top of *Transactional Business Process* template
* Uses *State Machine* layout for the phases of automation project
* Offers high level logging, exception handling and recovery
* Keeps external settings in *Config.xlsx* file and Orchestrator assets
* Pulls credentials from Orchestrator assets and *Windows Credential Manager*
* Gets transaction data from Orchestrator queue and updates back status
* Takes screenshots in case of system exceptions


### How It Works ###

1. **INITIALIZE PROCESS**
 + ./Framework/*InitiAllSettings* - Load configuration data from Config.xlsx file and from assets
 + ./Framework/*GetAppCredential* - Retrieve credentials from Orchestrator assets or local Windows Credential Manager
 + ./Framework/*InitiAllApplications* - Open and login to applications used throughout the process

2. **GET TRANSACTION DATA**
 + ./Framework/*GetTransactionData* - Fetches transactions from an Orchestrator queue defined by Config("OrchestratorQueueName") or any other configured data source

3. **PROCESS TRANSACTION**
 + *Process* - Process trasaction and invoke other workflows related to the process being automated 
 + ./Framework/*SetTransactionStatus* - Updates the status of the processed transaction (Orchestrator transactions by default): Success, Business Rule Exception or System Exception

4. **END PROCESS**
 + ./Framework/*CloseAllApplications* - Logs out and closes applications used throughout the process


### For New Project ###

1. Check the Config.xlsx file and add/customize any required fields and values
2. Implement InitiAllApplications.xaml and CloseAllApplicatoins.xaml workflows, linking them in the Config.xlsx fields
3. Implement GetTransactionData.xaml and SetTransactionStatus.xaml according to the transaction type being used (Orchestrator queues by default)
4. Implement Process.xaml workflow and invoke other workflows related to the process being automated

# Proyecto de Automatización RPA (UiPath) - Curso de Hiberus

## Descripción

Este proyecto fue desarrollado como parte del curso de RPA (UiPath) en la empresa Hiberus. Se trata de un proceso automatizado que utiliza el IDE UiPath para realizar tareas específicas en la página de ACME.

## Tareas Automatizadas

1. Abre el navegador Chrome.
2. Inicia sesión en la página de ACME utilizando credenciales predefinidas.
3. Navega hasta la pestaña "Work Items" para obtener información de proveedores cuyo tipo sea "WI5".
4. Accede a una página para obtener el código SHA1 a partir de la información del proveedor.
5. Regresa a la página de ACME y añade un comentario a cada proveedor cuyo tipo sea "WI5" con el contenido del respectivo código SHA1 obtenido.
6. Cierra sesión en la página de ACME.
7. Cierra el navegador Chrome.

## Advertencia

Este proyecto se encuentra desatendido y puede experimentar problemas de funcionamiento debido a las actualizaciones en la página de ACME y en Google Chrome. Se recomienda revisar y actualizar el proyecto según las últimas versiones y cambios en las herramientas utilizadas.

## Tecnologías Utilizadas

- UiPath (IDE de Automatización)
- Google Chrome (Navegador Web)


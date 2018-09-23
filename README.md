# Reciclart
*El arte de reciclar*

**Reciclart** es un proyecto que nace de iniciativa de llevar un sistema de beneficios para aquel que ayuda al planeta reciclando materiales.


### Entendimiento del Negocio


Elaborar un sistema que realice el control de puntos de reciclaje a través de un monedero electrónico en el cual las personas puedan ir a los puntos de reciclaje. De acuerdo a una tabla de precios, el sistema deberá identificar qué material se está entregando, y darle al usuario una parte proporcional de monedas en base al peso de lo que se entregó. Una persona puede entregar varios tipos de material, pero las monedas serán las mismas.

El usuario puede tener una firma electrónica, que deberá ser única e inmutable, por lo que se deberá utilizar tecnología blockchain para el intercambio de monedas. La firma deberá generar un código QR.


### Proceso

 - El usuario debe registrarse en el sistema con su CURP y un correo electrónico para las notificaciones. Cuando se registre se tiene que validar que el CURP válido (de ser posible que traiga los datos del usuario) y el usuario debe confirmar el registro por correo electrónico.

 - Una vez registrado podrá ingresar al sistema, este le generará una firma electrónica única con la cual podrá tener acceso al monedero, dentro del sistema el usuario podrá completar sus datos, entre los cuales debe ingresar número telefónico y dirección.

 - Las opciones del sistema para el usuario son:

	 - Perfil: aquí se deberán mostrar los datos del usuario, además de la 
   firma electrónica y aquí mismo el usuario podrá editar los datos de 
   contacto.

	- Monedero: aquí el usuario puede ver la cantidad de monedas que tiene, así como el histórico de movimientos, este debe incluir las ventas y compras.

	- Centros de reciclaje: aquí debe mostrar un listado de los centros de reciclaje cercanos a la ubicación del usuario, así como una opción para ver el mapa. Los filtros deben ser de acuerdo a estos criterios:

		-	Materiales, se puede seleccionar más de un material a buscar.

		- Horarios: aquí debe mostrar un filtro de hora de apertura y cierre.

		- Nombre: deberá ser por aproximación.

	- Empresas: aquí deben mostrarse las empresas donde se pueden intercambiar las monedas por productos o servicios, dentro se deben incluir filtros:

		-	Nombre de la empresa: búsqueda por aproximación.

		-	Producto o servicio: por aproximación

		-	Horarios: aquí debe mostrar un filtro de hora de apertura y cierre.

	-	Página principal: el usuario verá el centro de reciclaje más cercano a su ubicación actual. También tendrá un botón para poder cobrar el material llevado al centro.

-	Las empresas asociadas tendrán su acceso al sistema, dentro del cual se presentarán las siguientes opciones:

	-	Transacciones: deberán reflejarse las compras que los usuarios han hecho con las monedas y el concepto de compra.

	-	Perfil: en esta sección las empresas podrán sus datos, los cuales se podrán editar, estos datos son:

		-	Nombre o Razón Social.

		-	Logotipo.

		-	Horarios.

		-	Productos o servicios disponibles (listado de productos intercambiables por monedas, incluye nombre y precio)

	-	Estadísticas: aquí se podrán ver los datos estadísticos de los usuarios que han intercambiado monedas en sus tiendas, dentro de los cuales deben estar estos datos:

		-	Datos de usuarios: cantidad de intercambios, sexo, edad, ubicaciones, sucursales (si es el caso).

		-	Datos de productos: cantidad de intercambios, popularidad, comparación con otras empresas.

	-	Página principal: habrá un botón para registrar una compra, la cual escaneará el código QR del cliente y el cliente tendrá que validar la compra desde su teléfono.

	-	Una vez realizado el intercambio las monedas se deben descontar del monedero del usuario y acumular en el perfil de la empresa, cuando se realice este intercambio, se debe notificar al usuario a través de correo electrónico y por push notifications.

### Requisitos del sistema

-	El sistema Web tendrá los siguientes criterios:
	- **ASP .NET Core 2.1** como framework en back end, utilizando las siguientes herramientas:
		- Autenticación con [ASP .NET Core Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-2.1&tabs=visual-studio)
		- Autorización con [JWT](https://auth0.com/blog/securing-asp-dot-net-core-2-applications-with-jwts/)
		- Acceso a datos con [Entity Framework](https://docs.microsoft.com/en-us/aspnet/core/data/ef-mvc/intro?view=aspnetcore-2.1)
		- Modelo de datos con Web API
		- Notificaciones real-time con [SignalR](https://docs.microsoft.com/en-us/aspnet/core/signalr/introduction?view=aspnetcore-2.1)
	-  **Angular 6** como framework en front-end
		- Principios de [Material Design](https://material.angular.io/)
		- Uso de Autenticación con [JWT](https://github.com/auth0/angular2-jwt/)
		- Notificaciones real-time con [SignalR](https://www.npmjs.com/package/ng2-signalr)
		- Estructura modular
	- **SQL Server** como base de datos
		- Uso de Stored Procedures para acceso a datos
		- Base de datos normalizada (incluir diagrama)
	- **GitHub** como control de versiones.
		- Únicamente un repositorio con las siguientes ramas:
			- **Desarrollo**: en esta rama se trabajará todo el desarrollo
			- **Testing**: en esta rama se liberan módulos ya listos a probar
			- **Master**: sólo se publican módulos aprobados en la rama testing.
	- **Unit Tests** de  Visual Studio para realizar pruebas unitarias.
	- **[Ethereum](https://www.ethereum.org/)** como plataforma blockchain

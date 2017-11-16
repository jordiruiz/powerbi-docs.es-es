## <a name="using-the-username-or-userprincipalname-dax-function"></a>Uso de la función DAX username() o userprincipalname()
Puede aprovechar las ventajas de las funciones DAX *username()* o *userprincipalname()* dentro del conjunto de datos. Puede usarlas dentro de expresiones en Power BI Desktop. Cuando publique el modelo, se utilizará dentro del servicio Power BI.

En Power BI Desktop, *username()* devolverá un usuario con el formato de *DOMINIO\Usuario* y *userprincipalname()* lo devolverá con el formato de *user@contoso.com* .

En el servicio Power BI, *username()* y *userprincipalname()* devolverán ambos el nombre principal de usuario (UPN) del usuario. Es similar a una dirección de correo electrónico.


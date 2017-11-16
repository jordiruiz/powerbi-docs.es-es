## <a name="define-roles-and-rules-within-power-bi-desktop"></a>Definir roles y reglas en Power BI Desktop
Puede definir roles y reglas en Power BI Desktop. Al publicar en Power BI, publicará también las definiciones de roles.

Si quiere aprovechar las ventajas de la seguridad dinámica, deberá habilitar el conmutador de versión preliminar Habilitar filtrado cruzado en ambas direcciones para DirectQuery. Esto permitirá que se apliquen el filtro cruzado y el filtro de seguridad en ambas direcciones.

![](./media/rls-desktop-define-roles/powerbi-desktop-preview-bi-directional-directquery.png)

Para definir los roles de seguridad, puede hacer lo siguiente.

1. Importar datos en el informe de Power BI Desktop o configurar una conexión de DirectQuery.
   
   > [!NOTE]
   > No puede definir roles en Power BI Desktop para conexiones dinámicas de Analysis Services. Debe hacerlo en el modelo de Analysis Services.
   > 
   > 
2. Seleccione la pestaña **Modelado**.
3. Seleccione **Administrar roles**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. Seleccione **Crear**.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. Proporcione un nombre para el rol. 
6. Seleccione la tabla a la que quiere aplicar una regla DAX.
7. Escriba las expresiones DAX. Esta expresión debe devolver true o false. Por ejemplo: [Id. de entidad] = "Valor".
   
   > [!NOTE]
   > Puede usar *username()* en esta expresión. Tenga en cuenta que *username()* tendrá el formato *DOMINIO\Usuario* en Power BI Desktop. En el servicio Power BI, estará en el formato del UPN del usuario. Como alternativa, puede usar *userprincipalname()*, que siempre devolverá el usuario en el formato de su nombre principal de usuario.
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. Después de haber creado la expresión DAX, puede seleccionar la casilla encima del cuadro de expresión para validar la expresión.
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. Seleccione **Guardar**.

No puede asignar usuarios a un rol en Power BI Desktop. Esto se lleva a cabo en el servicio Power BI. Para habilitar la seguridad dinámica en Power BI Desktop, puede usar las funciones DAX *username()* y *userprincipalname()*. Las relaciones deben estar configuradas correctamente.


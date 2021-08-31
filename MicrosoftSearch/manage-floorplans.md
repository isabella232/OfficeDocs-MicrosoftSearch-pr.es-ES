---
title: Administrar planos de planta
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: La característica de planos de planta Búsqueda de Microsoft ayuda a los usuarios a encontrar personas, oficinas y otras comodidades dentro de un edificio.
ms.openlocfilehash: beeef26cc7413da654cc3ab01d92aa6cdc74e5cb
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702025"
---
# <a name="manage-floor-plans"></a>Administrar planos de planta

Los planes de planta **Búsqueda de Microsoft** ayudar a los usuarios a encontrar personas y salas de reuniones dentro de un edificio. Los planes de planta responden a las siguientes preguntas:

- ¿Dónde está la oficina de Allan Deyoung?
- Edificio 2 planta 3
- Buscar 2/11173

## <a name="add-floor-plans"></a>Agregar planos de planta

Siga estos pasos para configurar las respuestas de los planes de planta **Búsqueda de Microsoft**.

### <a name="step-1-determine-your-building-codes"></a>Paso 1: Determinar los códigos de creación

Los códigos de creación se usan como parte de la ubicación de la oficina de un usuario. Usará estos códigos al actualizar perfiles de usuario. Supongamos que su organización tiene un edificio en esta ubicación: *Edificio 2, 350 5th Avenue, Nueva York, NY 10016*

Estos son algunos ejemplos de código de este edificio: 2, B2, Building2, Building 2 o NYCB2. Cada edificio debe tener un código único.

### <a name="step-2-review-your-floor-plans"></a>Paso 2: Revisar los planes de planta

Los archivos de planos de planta deben estar en formato DWG; Los archivos DWG pueden contener etiquetas de texto. Cuando una etiqueta de texto marca una sala, se denomina etiqueta de sala. El archivo DWG debe tener **al menos 10 salas marcadas** con etiquetas. Estos son algunos ejemplos de archivos DWG con diferentes tipos de etiquetas:

|**Etiquetas de texto, incluidas las etiquetas de sala**|**Etiquetas de texto pero sin etiquetas de sala**|**Sin etiquetas de texto**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels.png.](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels.png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels.png](media/floorplans-nolabels.png)|

Consulta la sección [preguntas](#frequently-asked-questions) más frecuentes para obtener información sobre la visualización y actualización de archivos DWG.

### <a name="step-3-update-office-locations-on-user-profiles"></a>Paso 3: Actualizar ubicaciones de oficina en perfiles de usuario

La ubicación de la oficina de un usuario es una combinación de un código de creación y una etiqueta de sala. Por ejemplo, si el código de creación es *2* y la etiqueta de la sala es *1173*, la ubicación de la oficina sería *2/1173*.

Agregar o actualizar ubicaciones de oficina para cada usuario de la organización. Puede cambiar la ubicación de la oficina en el perfil de usuario en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) o puede cambiar en su Active Directory local para sincronizarse con Azure Active Directory. *PhysicalDeliveryOfficeName* es el campo que se usa para la ubicación de la oficina. Si las etiquetas de la sala no incluyen números de planta, consulta las preguntas más frecuentes para obtener sugerencias.

En este ejemplo, la oficina de Allan está en la sala 1173 de la planta 1 del edificio 2.
![floorplans-userlestview.png.](media/floorplans-userlistview.png)

> [!NOTE]
> Para ver las ubicaciones de oficina actualizadas al buscar planes de planta, debe actualizar las ubicaciones de oficina para al menos **10 personas** en cada planta.

### <a name="step-4-verify-office-location"></a>Paso 4: Comprobar la ubicación de la oficina

Use **Búsqueda de Microsoft** para buscar un usuario y comprobar que su ubicación de oficina aparece correctamente. Si acaba de actualizar las ubicaciones, es posible que deba esperar hasta **72** horas para que las actualizaciones aparezcan en los resultados de la búsqueda.

![floorplans-peoplecard.png.](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>Paso 5: Agregar ubicaciones de creación

Los planos de planta [usan Ubicaciones](manage-locations.md) para definir los edificios. En el [Centro de administración de Microsoft 365](https://admin.microsoft.com), vaya a [**Ubicaciones**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)y, a continuación, seleccione **Agregar**. Escriba el nombre, la dirección y las palabras clave del edificio. Agrega tantos edificios como necesites.

![floorplans-locations.png.](media/floorplans-locations.png)

Para obtener más información acerca de las ubicaciones, consulte [Administrar ubicaciones](manage-locations.md)

### <a name="step-6-gather-and-organize-office-locations"></a>Paso 6: Recopilar y organizar ubicaciones de oficina

Para poder usar los planos de planta, las ubicaciones de oficina deben indizarse. Se trata de una operación única que puede tardar hasta 48 horas en completarse. El tiempo total dependerá del tamaño de la organización.

En [el Centro de administración,](https://admin.microsoft.com)vaya a Planos de [**planta**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)y, a continuación, **seleccione Introducción.** Si no ve este aviso, este paso ya se ha completado para su organización

![floorplans_hydrationstep.png.](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>Paso 7: Upload planos de planta

1. En el [Centro de administración,](https://admin.microsoft.com)vaya a [**Planos de planta**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans).
2. Seleccione un edificio en la lista desplegable y seleccione **Siguiente**. Si el edificio no aparece en la lista, vuelva atrás y [agregue ubicaciones de creación.](#step-5-add-building-locations)
3. Seleccione **Upload archivos y,** a continuación, elija el plan de planta que está cargando.
4. Una vez completada la carga, debe escribir el número de planta que se representa en el archivo de plano de planta. Después, seleccione **Siguiente**.
5. (Opcional) Si el piso tiene alerones o zonas, escriba ese detalle.
6. Verá una pantalla de revisión que muestra cuántas ubicaciones de oficina se asignaron a los planos de planta. Seleccione **Detalles** para asegurarse de que la asignación es correcta.
    - Si no hay usuarios asignados o no está satisfecho con la asignación, seleccione **Continuar asignación**. Para publicar, seleccione **Omitir y publicar**.
7. Escriba el código de creación de este plan de planta. El código de creación se puede encontrar en la propiedad de ubicación de la oficina de los usuarios. Por ejemplo, si la ubicación de la oficina de un usuario es **2/1173**, el código de creación es **2**.
8. En la pantalla de revisión, repita el paso 6 para asegurarse de que la asignación es correcta.
9. (Opcional) Revise e identifique los patrones de ubicación de todos los planos de planta cargados y, a continuación, **seleccione Siguiente**.
10. En la pantalla de revisión, repita el paso 6 para asegurarse de que la asignación es correcta.
11. Cuando esté listo, seleccione **Publicar** para que el plan de planta esté disponible en **Búsqueda de Microsoft**.

> [!NOTE]
> **Los planes de planta tardan 48 horas en publicarse.** Después, los usuarios verán los resultados de un plan de planta similar al siguiente cuando busquen la oficina de un compañero de trabajo.

![floorplans-officelocation.png.](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>Paso 8: (opcional) Especificar patrones de ubicación

Después de cargar un plan de planta, las etiquetas de texto se compararán con las ubicaciones de oficina en los perfiles de los usuarios. Si hay menos de 10 coincidencias, aparecerá la pantalla Especificar patrones **de** ubicación. Los patrones de ubicación se usan para extraer información de piso, ala y sala de ubicaciones de oficina.

![floorplans-locationpattern.png.](media/floorplans-locationpattern.png)

Solo se requiere sala, el piso y el ala son opcionales y puede omitir ubicaciones según sea necesario.

## <a name="edit-floor-plans"></a>Editar planos de planta

Para actualizar un plan de planta existente, seleccione el plan de planta que desea cambiar y, a continuación, **seleccione Editar**. Realice los cambios y guárdelos.

## <a name="troubleshooting"></a>Solución de problemas

|**Paso**|**Mensaje de error**|**Tipo**|**Acción**|
|:-----|:-----|:-----|:-----|
|Upload planos de planta|No se puede leer CC_1.dwg. Vuelva a cargar o eliminar el plan de planta.|Error|Intente cargar el archivo de nuevo. Si eso no funciona, elimine el archivo e inténtelo de nuevo.|
|Upload planos de planta|Hay dos archivos denominados CC_1.dwg. Elimine uno de ellos o vuelva a cargarlo con otro nombre.|Error|Si el nombre del archivo es incorrecto, haga que el nombre de archivo sea único agregando información de piso o ala y, a continuación, cargue el archivo de nuevo. Si agregaste accidentalmente el mismo archivo dos veces, simplemente elimínelo.|
|Upload planos de planta|No se encontraron datos.|Error|Compruebe el archivo para asegurarse de que es el correcto y, a continuación, vuelva a cargarlo o elimínelo.|
|Upload planos de planta|Faltan referencias externas en este archivo. Cargue CC_1_furniture.dwg o elimine este archivo.|Advertencia|Upload archivos de referencia externos o eliminar.|
|Upload planos de planta|No se pudieron leer los números de sala ni las etiquetas en el archivo DWG. Elimine este archivo.|Advertencia|Compruebe el archivo DWG para asegurarse de que los datos están incluidos y, a continuación, elimine el archivo e inténtelo de nuevo.|
|Vincular ubicaciones de oficina|No se encuentran ubicaciones de oficina en Azure Active Directory. Agregue datos de ubicación a Azure Active Directory antes de configurar los planes de planta.|Error|[Actualizar ubicaciones de oficina en perfiles de usuario](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>Preguntas frecuentes.

**P:** ¿Cómo puedo ver y editar archivos DWG?

**A:** Use cualquiera de estas opciones para ver archivos DWG:

- Upload el archivo para SharePoint y abrirlo.
- Abra el archivo en [Microsoft Visio](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5) o en Autodesk [DWG TrueView](https://www.autodesk.com/products/dwg).
- Upload el archivo al [Visor en línea de Autodesk](https://viewer.autodesk.com/).

**P:** ¿Cómo agredo etiquetas de texto a salas sin marcar?

**A:** Abra el archivo DWG en un editor y [agregue etiquetas de salón.](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html)

**P:** ¿Cómo puedo crear o editar archivos DWG con fines de prueba?

**A:** Cree un archivo DWG en Microsoft Visio, En AutoCAD de Autodesk o en cualquier otro editor de DWG. Asegúrese de que 10 o más salas están etiquetadas en el archivo.

**P:** ¿Cuál es el mejor formato para etiquetas de texto en archivos DWG?

**A:** Para obtener los mejores resultados, las etiquetas de texto deben contener números de planta y números de sala. Los ejemplos siguientes usan 2 o SC para el código de creación.
<!-- markdownlint-disable no-inline-html -->
|Tipos de etiquetas de sala|Floor|Sala|Etiqueta de texto de ejemplo|Office ubicación (código de creación/etiqueta de texto)|
|:-----|:-----|:-----|:-----|:-----|
|Tiene el piso y el número de sala|1|173|1173|2/1173|
|| 21|45|21045|2/21045|
||23|100K|23-100K|23/23-100K|
||1|G06-07|1G06-07|2/1G06-07|
||2|1024A|02.1024A|2/02.1024A|
||2|1024A|02.1024A|2/02.1024A|
||2|105.01|2105.01|2/2105.01|
|Tiene código de edificio, piso y número de sala|0|X-11-M-12|2-0-X-11-M-12|2/2-0-X-11-M-12<br/>2-0-X-11-M-12|
||2|128A|22128A|2/22128A<br/>22128A|
||1|B2-11|21-B2-11|21/21-B2-11<br/>21-B2-11|
||2|45|SC2045|SC/SC2045<br/>SC2045|

**P:** ¿Puedo usar un archivo DWG que no incluya números de planta?

**A:** Sí, puede. Al actualizar las ubicaciones de oficina en el perfil de Azure Active Directory usuario, incluya el número de planta como parte del número de sala, incluso si falta en el archivo DWG. Después de cargar el archivo, aparecerá la pantalla Especificar patrones de ubicación y puede indicar ambos valores.

Por ejemplo, un archivo DWG que incluye números de sala, pero no números de planta, puede tener un aspecto similar al siguiente:

![floorplans-nofloors.png.](media/floorplans-nofloors.png)

La ubicación de la oficina en el perfil del usuario debe ser 2/1175 donde "2" es el código de creación, "1" es el número de planta y "175" es el número de sala.

---
title: Administrar planos de planta
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.date: 11/01/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: La característica de planos de planta de Microsoft Search ayuda a los usuarios a encontrar personas, oficinas y otras amenities en un edificio.
ms.openlocfilehash: 68912a8f440443c14cbc27019c7b30dc2d7a34c6
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "37950052"
---
# <a name="manage-floor-plans"></a>Administrar planos de planta

Los planes de planta de Microsoft Search ayudan a los usuarios a encontrar personas y salas de reuniones dentro de un edificio. Los planes de planta responden a estas preguntas:
- ¿Dónde se encuentra la oficina de Allan-Young?
- ¿Dónde se encuentra la sala de reuniones C1?

![Mapa de plano de planta que identifica la ubicación de la oficina del usuario dentro del edificio.](media/floorplans-officelocation.png)

Para que sea más fácil encontrar respuestas a preguntas como estas, la información sobre los edificios, las oficinas y las instalaciones de una organización debe estar disponible y ser buscada. Las organizaciones más grandes suelen tener equipos o equipos de administración de espacio y es posible que ya tenga esta información disponible. En una organización más pequeña, es posible que el administrador de la búsqueda tenga que crear y agregar.

## <a name="48-hours-before-you-begin"></a>48 horas antes de empezar
Antes de empezar a cargar los planes de planta, debe indizar las ubicaciones de oficina de los usuarios. Según el tamaño de su organización, puede tardar hasta 48 horas en completarse. Si omite este paso, recibirá errores al realizar el procedimiento.

![Página captura de pantalla de planos de planta con la advertencia "Microsoft debe recopilar y organizar las ubicaciones de oficina antes de que se puedan cargar los planes de planta".](media/floorplans_hydrationstep.png)

En el centro de [Administración](https://admin.microsoft.com)de Microsoft 365, vaya a **configuración** > de los**planes de planta**de**Microsoft Search** > y, a continuación **, seleccione introducción**.

Si no ve este aviso, usted o alguien de su organización ya ha iniciado este paso.

## <a name="things-to-consider"></a>Consideraciones que se deben tener en cuenta
Para ayudar a los usuarios a encontrar información sobre las oficinas y las instalaciones de creación, debe agregar:

|Motivos     |¿Por qué es importante?  |
|---------|---------|
|Ubicación del edificio    |    Deberá agregar cada edificio a las ubicaciones de Microsoft Search. Debe elaborar un formato de nombre estándar para cada edificio. Puede Agregar el edificio usando una dirección postal o coordenadas de mapa.     |
|Propiedad **Office** en todas las cuentas de usuario     |    Cada cuenta de usuario debe tener la propiedad **Office** en su ubicación de oficina. Y las ubicaciones de la oficina deben seguir un formato estándar e incluir la información sobre el edificio, el suelo y el salón.   <br> En Azure AD, esta propiedad se denomina **PhysicalDeliveryOfficeName**.    |
|Archivo de plano de planta en formato DWG     |   Necesita un plano de planta independiente para cada planta o ala del edificio e incluir la información de la oficina en el mismo formato que usó en la propiedad de Office del usuario. El archivo debe estar en formato DWG de dibujo de AutoCAD. |

Para obtener más información, consulte [Best Practices for Microsoft Search Floor Plans](floorplans-bestpractices.md).

## <a name="building-location"></a>Ubicación del edificio

Identifique los edificios que deben agregarse como ubicaciones. La dirección de ubicación y las coordenadas de mapa de un edificio son el primer punto de identificación. Si el edificio no se agrega todavía como una ubicación, el administrador tiene que agregarlo. Consulte [Manage locations](manage-locations.md) para obtener más información.

## <a name="floor-plans-files"></a>Archivos de planos de planta

Una vez identificado un edificio, puede agregar sus planes de planta. Todos los archivos de los planes de planta deben tener formato DWG. Si su organización aún no las tiene, deberá crear los planos de planta en una aplicación compatible con DWG. Los planos de planta deben asignar correctamente todos los salones, como salas de reuniones o reuniones, aseos, cocinas, salas de correo y otras instalaciones en cada planta del edificio para habilitar la búsqueda.

### <a name="office-locations"></a>Ubicaciones de oficina

Para asignarlos a planos de planta, todas las ubicaciones de oficina y los datos de oficina de los empleados deben estar en la cuenta del usuario. En el plano de planta, las ubicaciones de la oficina deben ser únicas y no pueden repetirse. Por ejemplo, si dos personas comparten Office 2/1173, **2/1173** solo puede tener una instancia única en los planes de planta, pero las cuentas de usuario de Azure ad tendrán la misma ubicación de la oficina.

![floorplans-peoplecard. png](media/floorplans-peoplecard.png)

 > [!Note] 
 > Cuando un usuario busca una sala o ubicación de la oficina de un colega, los números de sala de los planes de planta coinciden con las ubicaciones de Office en Azure AD. Si se encuentra una coincidencia, se muestra el mapa.

## <a name="add-floor-plan"></a>Agregar plano de planta

 La primera vez que vaya a planes de planta, es posible que vea una nota en la parte superior de la página que indica, *Microsoft necesita recopilar y organizar las ubicaciones de oficina*para poder cargar los planes de planta. Seleccione Introducción a indizar las **ubicaciones de Azure** ad Office. 

1. En el [centro de administración](https://admin.microsoft.com), vaya a **configuración** > de los**planes de planta**de**Microsoft Search** >y, a continuación, seleccione **Agregar planes de planta**.
4. Seleccione el edificio en la lista desplegable y seleccione **siguiente**. Si el edificio no aparece en la lista, debe agregarlo en ubicaciones. Consulte [Manage locations](manage-locations.md) para obtener más información.
6. Seleccione **cargar archivos**y, a continuación, seleccione el plano de planta que desea cargar. 
1. Una vez que el archivo se carga correctamente, debe identificar cómo se representa el número de piso o ala. 
7. Especifique el código que identifica el edificio. El código de edificio puede encontrarse en la cuenta del usuario en la propiedad ubicación de la **Oficina** . Por ejemplo, si la ubicación de la oficina del usuario es **2/1173**, el código de creación es **2**. 
9. Revise e identifique los patrones de ubicación de todos los planes de planta cargados y, a continuación, seleccione **siguiente**.
10. Cuando esté listo, seleccione **publicar** para que el plano de planta pueda buscarse.

> [!Note] 
> Cuando un plano de planta está en estado borrador, está incompleto. Un borrador permite coordinar las partes interesadas para cargar y crear planos de planta. También le permite implementar planes de planta por fases.

## <a name="edit-floor-plans"></a>Editar planos de planta

1. En el [centro de administración](https://admin.microsoft.com), vaya a **configuración** > de los**planes de planta**de**Microsoft Search** > . 
1. Seleccione **publicada** o **borrador**, seleccione el plano de planta que desee cambiar y, a continuación, seleccione **Editar**.
5. Realice los cambios y, a continuación, seleccione **Guardar**.

## <a name="troubleshoot-errors"></a>Solucionar errores

No puedes ir al paso siguiente para definir la información sobre el suelo, el ala y la habitación hasta que se corrijan todos los errores. El siguiente archivo de tabla carga los mensajes de error y las acciones para corregir los problemas.

| Mensaje de error   | Tipo    | Action       |
|:----------------| :--------- | :-------------- |
| No se puede leer CC_1. dwg. Vuelva a cargar o eliminar el plano de planta. | Error |  Intente cargar el archivo de nuevo. Si esto no funciona, elimine el archivo y vuelva a intentarlo. |
| Hay dos archivos con el nombre CC_1. dwg. Elimine uno de ellos o vuelva a cargarlo con otro nombre.| Error | Si el nombre de archivo es incorrecto, haga que el nombre del archivo sea único agregando información de suelos o alas y, a continuación, vuelva a cargar el archivo. <br><br>Si agregó por accidente el mismo archivo dos veces, simplemente elimínelo. |
| No se encontraron datos. | Error | Compruebe el archivo para asegurarse de que es el correcto y, a continuación, cárguelo de nuevo o elimínelo. |
| Faltan referencias externas en este archivo. Cargue "CC_1_furniture. DWG" o elimine este archivo. | Advertencia | Cargar archivos de referencia externos o eliminar.|
| No se pudieron leer los números o las etiquetas del salón en el archivo DWG. Elimine este archivo. | Advertencia | Compruebe el archivo DWG para asegurarse de que se incluyen los datos y, a continuación, elimine el archivo y vuelva a intentarlo. |

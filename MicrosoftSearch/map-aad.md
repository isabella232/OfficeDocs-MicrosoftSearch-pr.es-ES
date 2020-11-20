---
title: Asignación de identidades de AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Pasos sobre cómo asignar identidades de AAD
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367707"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="583d0-103">Asignar las identidades de Azure AD</span><span class="sxs-lookup"><span data-stu-id="583d0-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="583d0-104">Este artículo le guiará por los pasos de la asignación de identidades de Azure AD a un identificador único para su origen de datos (identidad que no es de Azure AD), de modo que los usuarios de la lista de control de acceso (ACL) con identidades que no son de Azure AD puedan ver los resultados de la búsqueda del conector en su ámbito.</span><span class="sxs-lookup"><span data-stu-id="583d0-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="583d0-105">Estos pasos solo son relevantes para los administradores de búsqueda que están configurando un conector de [Salesforce](salesforce-connector.md) por Microsoft con los permisos de búsqueda de "solo personas con acceso a este origen de datos" e identidad tipo "AAD".</span><span class="sxs-lookup"><span data-stu-id="583d0-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="583d0-106">Los siguientes pasos le guiarán por el proceso de asignación de las propiedades de usuario de Azure AD a los **identificadores de Federación** de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="583d0-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="583d0-107">Si está configurando un [conector de Salesforce](salesforce-connector.md) y **selecciona solo personas con acceso a este origen de datos** y un tipo de identidad **que no es AAD** en la pantalla de permisos de búsqueda, consulte el artículo sobre [mapas de identidades que no son de Azure ad](map-non-aad.md) para conocer los pasos sobre cómo asignar identidades que no son de Azure ad.</span><span class="sxs-lookup"><span data-stu-id="583d0-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="583d0-108">Pasos para asignar las propiedades de Azure AD</span><span class="sxs-lookup"><span data-stu-id="583d0-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="583d0-109">1. seleccionar Propiedades de usuario de Azure AD para asignar</span><span class="sxs-lookup"><span data-stu-id="583d0-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="583d0-110">Puede seleccionar las propiedades de Azure AD que necesita asignar al identificador de Federación.</span><span class="sxs-lookup"><span data-stu-id="583d0-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="583d0-111">Puede seleccionar una propiedad de usuario de Azure AD en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="583d0-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="583d0-112">También puede Agregar tantas propiedades de usuario de Azure AD como quiera si estas propiedades son necesarias para crear la asignación del identificador de Federación de su organización.</span><span class="sxs-lookup"><span data-stu-id="583d0-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="583d0-113">2. crear una fórmula para completar la asignación</span><span class="sxs-lookup"><span data-stu-id="583d0-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="583d0-114">Puede combinar los valores de las propiedades de usuario de Azure AD para formar el identificador de Federación único.</span><span class="sxs-lookup"><span data-stu-id="583d0-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="583d0-115">En el cuadro de fórmula, " {0} " corresponde a la *primera* propiedad de Azure ad que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="583d0-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="583d0-116">" {1} " corresponde a la *segunda* propiedad de Azure ad que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="583d0-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="583d0-117">" {2} " corresponde a la *tercera* propiedad de Azure ad, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="583d0-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="583d0-118">A continuación se muestran algunos ejemplos de fórmulas con salidas de expresión regular de ejemplo y resultados de fórmulas:</span><span class="sxs-lookup"><span data-stu-id="583d0-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="583d0-119">Fórmula de ejemplo</span><span class="sxs-lookup"><span data-stu-id="583d0-119">Sample formula</span></span>                  | <span data-ttu-id="583d0-120">Valor de {0} la propiedad para un usuario de muestra</span><span class="sxs-lookup"><span data-stu-id="583d0-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="583d0-121">Valor de {1} la propiedad para un usuario de muestra</span><span class="sxs-lookup"><span data-stu-id="583d0-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="583d0-122">Resultado de la fórmula</span><span class="sxs-lookup"><span data-stu-id="583d0-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="583d0-123">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="583d0-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="583d0-124">Name</span><span class="sxs-lookup"><span data-stu-id="583d0-124">firstname</span></span> | <span data-ttu-id="583d0-125">Apellido</span><span class="sxs-lookup"><span data-stu-id="583d0-125">lastname</span></span> |<span data-ttu-id="583d0-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="583d0-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="583d0-127">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="583d0-127">{0}@domain.com</span></span>                 | <span data-ttu-id="583d0-128">identificado</span><span class="sxs-lookup"><span data-stu-id="583d0-128">userid</span></span>                 |             |<span data-ttu-id="583d0-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="583d0-129">userid@domain.com</span></span>

<span data-ttu-id="583d0-130">Después de proporcionar la fórmula, puede hacer clic opcionalmente en **vista previa** para ver una vista previa de 5 usuarios aleatorios del origen de datos con sus correspondientes asignaciones de usuario aplicadas.</span><span class="sxs-lookup"><span data-stu-id="583d0-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="583d0-131">El resultado de la vista previa incluye el valor de las propiedades de usuario de Azure AD seleccionadas en el paso 1 para los usuarios y el resultado de la fórmula final que se proporciona en el paso 2 para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="583d0-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="583d0-132">También indica si los resultados de la fórmula podrían resolverse en un usuario de Azure AD del espacio empresarial a través de un icono de "éxito" o "error".</span><span class="sxs-lookup"><span data-stu-id="583d0-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="583d0-133">Todavía puede continuar con la creación de la conexión si una o más asignaciones de usuario tienen el estado "error" después de hacer clic en **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="583d0-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="583d0-134">La vista previa muestra 5 usuarios aleatorios y sus asignaciones desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="583d0-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="583d0-135">Si la asignación que proporciona no asigna todos los usuarios, es posible que experimente este caso.</span><span class="sxs-lookup"><span data-stu-id="583d0-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="583d0-136">Ejemplo de asignación de Azure AD</span><span class="sxs-lookup"><span data-stu-id="583d0-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="583d0-137">Vea la siguiente instantánea para obtener una asignación de Azure AD de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="583d0-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Instantánea de ejemplo de cómo rellenar la página de asignación de Azure AD](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="583d0-139">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="583d0-139">Limitations</span></span>  

- <span data-ttu-id="583d0-140">Solo se admite una asignación para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="583d0-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="583d0-141">No se admiten las asignaciones condicionales.</span><span class="sxs-lookup"><span data-stu-id="583d0-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="583d0-142">No puede cambiar la asignación una vez publicada la conexión.</span><span class="sxs-lookup"><span data-stu-id="583d0-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="583d0-143">Las expresiones basadas en regex contra las propiedades de usuario de Azure AD no son compatibles con la transformación de ID de Federación de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="583d0-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>
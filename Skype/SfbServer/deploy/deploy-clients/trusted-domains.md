---
title: Skype Room System の信頼されたドメイン
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System と Skype for Business の信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834117"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="03421-103">Skype Room System の信頼されたドメイン</span><span class="sxs-lookup"><span data-stu-id="03421-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="03421-104">このトピックでは、Skype Room System と Skype for Business の信頼されたドメインを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03421-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="03421-105">信頼済みドメイン</span><span class="sxs-lookup"><span data-stu-id="03421-105">Trusted domains</span></span>

<span data-ttu-id="03421-106">サインインするユーザー アカウントの SIP ドメインが、証明書のサブジェクト名またはサブジェクトの代替名に表示される名前と異なる場合、Skype for Business クライアントは Skype for Business Server からの証明書を受け入れ可能なダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="03421-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="03421-107">組織内の Skype for Business Server 用に構成された証明書に、サブジェクト名またはサブジェクト代替名に Skype Room System アカウントの SIP ドメイン名が設定されていない場合は、Skype Room System コンソール コンピューターの信頼されたドメイン レジストリ キーの下にある証明書に表示されるドメインを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03421-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="03421-108">Skype Room System の製造元が提供する Skype Room System Administrator's Guide では、Skype for Business クライアントで信頼されたドメインを追加する方法と場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="03421-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="03421-109">たとえば、Skype for Business Server で構成された証明書のサブジェクト/サブジェクトの代替名が "CONTOSO" だとします。LOCAL" と Skype Room System サインイン アドレスのユーザーに割り当てられている SIP ドメインの 1 つが "confrm1@contoso.net" です。</span><span class="sxs-lookup"><span data-stu-id="03421-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="03421-110">contoso.net は証明書に含めないので、Skype Room System の製造元が提供する Skype Room System 管理者ガイドで説明したように、レジストリで "contoso.local" を信頼されたドメインとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03421-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  


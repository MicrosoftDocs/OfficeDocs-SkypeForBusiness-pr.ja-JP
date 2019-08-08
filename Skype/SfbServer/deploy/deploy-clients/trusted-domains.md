---
title: Skype Room System の信頼されたドメイン
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235016"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="93c07-103">Skype Room System の信頼されたドメイン</span><span class="sxs-lookup"><span data-stu-id="93c07-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="93c07-104">このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="93c07-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="93c07-105">信頼されたドメイン</span><span class="sxs-lookup"><span data-stu-id="93c07-105">Trusted domains</span></span>

<span data-ttu-id="93c07-106">Skype for Business クライアントに表示されるダイアログボックスを使用すると、ユーザーアカウントの SIP ドメインが証明書のサブジェクト名またはサブジェクト名に表示される名前とは異なる場合に、ユーザーが Skype for Business Server の証明書を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="93c07-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="93c07-107">組織内の Skype for Business Server 用に構成された証明書に、Skype Room System アカウントの SIP ドメイン名がサブジェクトまたはサブジェクトの代替名に含まれていない場合は、信頼済みドメインの証明書に記載されているドメインを構成する必要があります。Skype Room System コンソールコンピューターのレジストリキー。</span><span class="sxs-lookup"><span data-stu-id="93c07-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="93c07-108">Skype Room システムの製造元によって提供される Skype Room システム管理者ガイドで、Skype for Business クライアントで信頼済みドメインを追加する方法と場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="93c07-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="93c07-109">たとえば、Skype for Business Server で構成されている証明書のサブジェクト/件名の代替名が "CONTOSO" であるとします。ローカル「Skype Room System サインインアドレス用にユーザーに割り当てられている SIP ドメインの1つは "confrm1@contoso.net" です。</span><span class="sxs-lookup"><span data-stu-id="93c07-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="93c07-110">Contoso.net は証明書に登録されていないため、Skype Room システムコンピューターでは、skype Room system のメーカーによって提供されている Skype room システム管理者ガイドで説明されているように、信頼できるドメインとして "コントソ .local" を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93c07-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  


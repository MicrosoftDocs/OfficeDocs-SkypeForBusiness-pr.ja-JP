---
title: Skype Room System の信頼されたドメイン
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: bc025849f56a7257ac3684b9783e551959bd0228
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214892"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="da28c-103">Skype Room System の信頼されたドメイン</span><span class="sxs-lookup"><span data-stu-id="da28c-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="da28c-104">このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da28c-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="da28c-105">信頼されたドメイン</span><span class="sxs-lookup"><span data-stu-id="da28c-105">Trusted domains</span></span>

<span data-ttu-id="da28c-106">ビジネス クライアント用の Skype では、ビジネスのサーバーのサインイン時にユーザー アカウントの SIP ドメインの証明書のサブジェクトまたはサブジェクトの alt キーを押し名の表示名と異なる場合、Skype からの証明書を受け入れるようにユーザーを許可する] ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da28c-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="da28c-107">それらのドメインが信頼されたドメイン] で [証明書の提示を構成する必要がある場合は、組織のビジネス サーバーの Skype 用に構成された証明書には、件名または件名の alt キーを押し、Skype ルームのシステム アカウントの SIP ドメインの名前がありません、Skype ルーム システム コンソール コンピューター上のレジストリ キーです。</span><span class="sxs-lookup"><span data-stu-id="da28c-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="da28c-108">Skype ルーム システムの製造元から提供された Skype ルーム システム管理者ガイド 』 の説明方法と場所、Skype ビジネス クライアント用の信頼されたドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="da28c-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="da28c-109">たとえば、Skype ビジネス サーバーの構成、証明書は、"CONTOSO の件名または件名の alt キーを押し名前を付けます。ローカル"と Skype ルーム システムのサインイン用アドレスのユーザーに割り当てられている SIP ドメインの 1 つは、「confrm1@contoso.net です」</span><span class="sxs-lookup"><span data-stu-id="da28c-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="da28c-110">Skype ルーム システム コンピューター上の証明書ではなく contoso.net であるため、Skype ルーム システムの製造元から提供された Skype ルーム システム管理者ガイド 』 で説明したように、レジストリ内の信頼されたドメインとして"contoso.local"を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da28c-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  


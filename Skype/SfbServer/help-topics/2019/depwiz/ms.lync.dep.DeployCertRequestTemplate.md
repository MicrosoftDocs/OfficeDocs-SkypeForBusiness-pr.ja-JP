---
title: 証明書要求 (テンプレートの指定)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
ROBOTS: NOINDEX, NOFOLLOW
description: '[別の証明書テンプレートの指定] ページでは、既定で使用される WebServer 証明書テンプレート以外の証明書テンプレートを定義できます。 [選択された証明機関に別の証明書テンプレートを使用する] チェック ボックスをオンにしてから、[証明書テンプレート名] テキスト ボックスで別の証明書テンプレートの名前を定義します。 証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。 前のページに戻るには、[戻る] をクリックします。 証明書要求プロセスを終了するには、[キャンセル] をクリックします。'
ms.openlocfilehash: 3940162eb8369942828018c84d0de69107110b37
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216292"
---
# <a name="certificate-request-specify-termplate"></a><span data-ttu-id="ae17b-107">証明書要求 (テンプレートの指定)</span><span class="sxs-lookup"><span data-stu-id="ae17b-107">Certificate Request (Specify Termplate)</span></span>
 
<span data-ttu-id="ae17b-p102">[**別の証明書テンプレートの指定**] ページでは、既定で使用される WebServer 証明書テンプレート以外の証明書テンプレートを定義できます。[**選択された証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにしてから、[**証明書テンプレート名**] テキスト ボックスで別の証明書テンプレートの名前を定義します。証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。前のページに戻るには、[**戻る**] をクリックします。証明書要求プロセスを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae17b-p102">The **Specify Alternate Certificate Template** page enables you to define a certificate template other than the WebServer certificate template that is used by default. Select the check box **Use alternate certificate template for selected certification authority**, and then define the name of the alternate certificate template in the text box **Certificate template name**. You must use the name of the template as it is defined in the certification authority (CA). Click **Back** to go back to the previous page. Click **Cancel** to end the certificate request process.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ae17b-p103">このオプションは、証明書を発行するときにパブリック CA のシステムで定義されている特定のテンプレートを使用するようパブリック CA から指示を受けた場合にのみ使用してください。内部 CA が証明書を発行する場合は、CA 管理者が、別の証明書テンプレートに使用する名前について指示します。このオプションは、組織で新しい WebServer テンプレートを定義しており、既定の WebServer テンプレートを無効にしている場合に特に有用です。</span><span class="sxs-lookup"><span data-stu-id="ae17b-p103">You should use this option only if you are advised by your public CA that you should use a specific template that is defined on their system for issuing certificates. If the certificate is being issued by your internal CA, your CA administrator should advise you what name to use for the alternate certificate template. This option is extremely valuable in cases where your organization has defined a new WebServer template and has disabled the default WebServer template.</span></span> 
  


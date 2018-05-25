---
title: 証明書要求 (テンプレートの指定)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: 代替証明書テンプレートの指定] ページを使用すると、既定で使用されている web サーバー証明書テンプレート] 以外の証明書テンプレートを定義できます。 テンプレートを選択した証明機関の場合は、代替の証明書] チェック ボックスを使うを選択し、テキスト ボックスの証明書テンプレートの名前で別の証明書テンプレートの名前を定義します。 証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。 前のページに戻るに戻る] をクリックします。 証明書要求の処理を終了するには [キャンセル] をクリックします。
ms.openlocfilehash: 856ad66b4bf2974e43e8684ca6016494df26019f
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="certificate-request-specify-termplate"></a><span data-ttu-id="90e1d-107">証明書要求 (テンプレートの指定)</span><span class="sxs-lookup"><span data-stu-id="90e1d-107">Certificate Request (Specify Termplate)</span></span>
 
<span data-ttu-id="90e1d-p102">[**別の証明書テンプレートの指定**] ページでは、既定で使用される WebServer 証明書テンプレート以外の証明書テンプレートを定義できます。[**選択された証明機関に別の証明書テンプレートを使用する**] チェック ボックスをオンにしてから、[**証明書テンプレート名**] テキスト ボックスで別の証明書テンプレートの名前を定義します。証明機関 (CA) で定義したのと同じテンプレート名を使用する必要があります。前のページに戻るには、[**戻る**] をクリックします。証明書要求プロセスを終了するには、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90e1d-p102">The **Specify Alternate Certificate Template** page enables you to define a certificate template other than the WebServer certificate template that is used by default. Select the check box **Use alternate certificate template for selected certification authority**, and then define the name of the alternate certificate template in the text box **Certificate template name**. You must use the name of the template as it is defined in the certification authority (CA). Click **Back** to go back to the previous page. Click **Cancel** to end the certificate request process.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="90e1d-p103">このオプションは、証明書を発行するときにパブリック CA のシステムで定義されている特定のテンプレートを使用するようパブリック CA から指示を受けた場合にのみ使用してください。内部 CA が証明書を発行する場合は、CA 管理者が、別の証明書テンプレートに使用する名前について指示します。このオプションは、組織で新しい WebServer テンプレートを定義しており、既定の WebServer テンプレートを無効にしている場合に特に有用です。</span><span class="sxs-lookup"><span data-stu-id="90e1d-p103">You should use this option only if you are advised by your public CA that you should use a specific template that is defined on their system for issuing certificates. If the certificate is being issued by your internal CA, your CA administrator should advise you what name to use for the alternate certificate template. This option is extremely valuable in cases where your organization has defined a new WebServer template and has disabled the default WebServer template.</span></span> 
  


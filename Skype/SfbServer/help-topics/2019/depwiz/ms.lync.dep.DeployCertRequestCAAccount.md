---
title: 証明書要求 (証明機関のアカウント)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 要求を送信するには、使用する証明機関 (CA) は、ユーザーとしてログインして現在のものとは別の資格情報を必要があります。
ms.openlocfilehash: 71239d8b4648c08de12b0c425c5050c5c4f2e0ed
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890214"
---
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="70733-103">証明書要求 (証明機関のアカウント)</span><span class="sxs-lookup"><span data-stu-id="70733-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="70733-104">要求を送信するには、使用する証明機関 (CA) は、ユーザーとしてログインして現在のものとは別の資格情報を必要があります。</span><span class="sxs-lookup"><span data-stu-id="70733-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="70733-105">別のユーザーとしての証明書要求を許可するには、**代替資格情報の証明機関を指定する**] チェック ボックスをオンにし、ユーザー名または_ドメイン_を入力し、\ 、証明書を要求できるユーザーの_ユーザー名_.</span><span class="sxs-lookup"><span data-stu-id="70733-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="70733-106">[**パスワード**] ボックスで、指定したユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="70733-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="70733-107">ユーザー名とパスワードは、オンライン CA に証明書の要求のプロセスのではなく、実際の証明書要求の一部として、送信されます。</span><span class="sxs-lookup"><span data-stu-id="70733-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  


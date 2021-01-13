---
title: 証明書要求 (証明機関のアカウント)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 要求を送信するために、証明機関 (CA) では、現在ログインしているユーザーとは別のユーザーの資格情報を必要とすることがあります。
ms.openlocfilehash: ab3e5f1d15b32e866a0a8a99f54ce8a1b3d81a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830347"
---
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="9555a-103">証明書要求 (証明機関のアカウント)</span><span class="sxs-lookup"><span data-stu-id="9555a-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="9555a-104">要求を送信するために、証明機関 (CA) では、現在ログインしているユーザーとは別のユーザーの資格情報を必要とすることがあります。</span><span class="sxs-lookup"><span data-stu-id="9555a-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="9555a-105">別のユーザーとして証明書要求を許可するには、[証明機関の別の資格情報を指定する] チェック ボックスをオンにして、証明書を要求できるユーザーのユーザー名またはドメイン ユーザー名を入力します。 \  </span><span class="sxs-lookup"><span data-stu-id="9555a-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="9555a-106">[**パスワード**] ボックスに、指定したユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9555a-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="9555a-107">ユーザー名とパスワードは、実際の証明書要求に含めてではなく、証明書要求プロセスの一部としてオンライン CA に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9555a-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  


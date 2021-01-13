---
title: 証明書要求 (結果)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: '[オンライン証明書要求の状態] ページには、オンライン証明書要求を適切に作成および発行した結果として、重要な情報が表示されます。 このページには、証明書を一意に識別する証明書の拇印が表示されます。 既定では、[この証明書を Skype for Business Server 証明書の使用法に割り当てる] チェック ボックスがオンになっています。 [完了] をクリックすると、証明書要求の作成手順で定義した目的で、証明書が Lync Server 2013 に自動的に割り当てられます。 既定では、証明書を割り当てる目的は次のとおりです。'
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805147"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="ab0f1-107">証明書要求 (結果)</span><span class="sxs-lookup"><span data-stu-id="ab0f1-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="ab0f1-108">[**オンライン証明書要求の状態**] ページには、オンライン証明書要求を適切に作成および発行した結果として、重要な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="ab0f1-109">このページには、証明書を一意に識別する証明書の拇印が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="ab0f1-110">既定では、[この証明書を **Skype for Business Server** 証明書の使用法に割り当てる] チェック ボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="ab0f1-111">[ **完了]** をクリックすると、証明書要求の作成手順で定義した目的で、証明書が Lync Server 2013 に自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="ab0f1-112">既定では、証明書を割り当てる目的は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="ab0f1-113">相互トランスポート層セキュリティ (MTLS) のサーバーの既定値 - クライアントおよび他のサーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="ab0f1-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="ab0f1-114">内部 Web サービス - トランスポート層セキュリティ/トランスポート層セキュリティ/トランスポート サーバー (TLS/SSL) 用Secure Sockets Layer Web サービス サイト上のクライアントおよびサーバー接続</span><span class="sxs-lookup"><span data-stu-id="ab0f1-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="ab0f1-115">外部 Web サービス - TLS/SSL 用の外部 Web サービス サイト上のクライアントおよびサーバー接続</span><span class="sxs-lookup"><span data-stu-id="ab0f1-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="ab0f1-116">[**証明書の詳細の表示**] をクリックすると、証明書を表示して、証明書のプロパティが正しい内容になっていることと、証明書を適用してサーバーで使用できる状態になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="ab0f1-117">[**完了**] をクリックすると、オンライン証明書要求プロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="ab0f1-118">[この証明書を Skype **for Business Server** 証明書の使用法に割り当てる] チェック ボックスをオンにした場合、証明書は自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="ab0f1-119">このチェック ボックスをオフにした場合は、別の手順で証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ab0f1-120">発行元証明機関 (CA) のルート証明書がコンピューターの信頼されたルート証明機関ストアに含されていない場合、または中間 CA 証明書が適切なストアに含されていない場合は、次の図に示す概要状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="ab0f1-121">証明書を割り当てるためのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="ab0f1-122">証明書の割り当てプロセスを完了するには、発行元の CA のルート証明書と任意の中間 CA 証明書をインポートし、メインの [証明書ウィザード] ページで [**割り当て**] をクリックして証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab0f1-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  


---
title: 証明書要求 (結果)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: オンライン証明書要求の状態のページは、その結果を正常に作成し、オンラインの証明書の要求の発行から重要な情報が表示されます。 このページには、証明書を一意に識別する証明書の拇印が用意されています。 既定では、Skype をビジネスのサーバー証明書の使用法の証明書を割り当てる] チェック ボックスが選択されます。 場合は [完了] をクリックすると、証明書に自動的に割り当てられます Lync Server 2013 に証明書の要求の作成手順を実行中に定義するために。 既定では、証明書が割り当てられるため。
ms.openlocfilehash: bedc5137085a36a296518048e5f0917e60dbe980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911087"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="e8680-107">証明書要求 (結果)</span><span class="sxs-lookup"><span data-stu-id="e8680-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="e8680-108">**オンライン証明書要求の状態**のページは、その結果を正常に作成し、オンラインの証明書の要求の発行から重要な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8680-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="e8680-109">このページには、証明書を一意に識別する証明書の拇印が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e8680-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="e8680-110">既定では、**ビジネスのサーバー証明書の使用状況を Skype に、この証明書を割り当てる**チェック ボックスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="e8680-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="e8680-111">**[完了**] をクリックする場合、証明書に自動的に割り当てられます Lync Server 2013 証明書の要求の作成手順を実行中に定義するために。</span><span class="sxs-lookup"><span data-stu-id="e8680-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="e8680-112">既定では、証明書が割り当てられるため。</span><span class="sxs-lookup"><span data-stu-id="e8680-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="e8680-113">サーバーの相互トランスポート層セキュリティ (MTLS) がクライアントに接続し、他のサーバーの既定値</span><span class="sxs-lookup"><span data-stu-id="e8680-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="e8680-114">トランスポート レイヤー セキュリティまたは Secure Sockets Layer (SSL または TLS) の web サービスの内部の内部の Web 上のクライアントとサーバーの接続のサービス サイト</span><span class="sxs-lookup"><span data-stu-id="e8680-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="e8680-115">TLS と SSL の web サービスの外部の外部の web クライアントとサーバーの接続のサービス サイト</span><span class="sxs-lookup"><span data-stu-id="e8680-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="e8680-116">証明書のプロパティが意図したと証明書が適用され、サーバー上に配置する準備ができていることを確認する証明書を表示するのには**証明書の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8680-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="e8680-117">オンライン証明書要求の処理を完了する**完了**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8680-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="e8680-118">**Skype ビジネス サーバー証明書の使用法のこの証明書を割り当てる**チェック ボックスを選択した場合、証明書が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e8680-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="e8680-119">このチェック ボックスをオフにする] を選択した場合は、別の手順で証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8680-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e8680-120">発行元証明機関 (CA) のルート証明書がコンピューターの信頼されたルート証明機関ストアにない場合、または中間 CA 証明書が適切なストアにない場合は、次の図に示すようにステータスの概要がわかります。</span><span class="sxs-lookup"><span data-stu-id="e8680-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="e8680-121">証明書を割り当てるオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="e8680-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="e8680-122">証明書の割り当てプロセスを完了するには発行元 CA のルート証明書と中間 CA 証明書をインポートし、証明書ウィザードのメイン ページで [**割り当て**] をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e8680-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  


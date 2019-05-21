---
title: 証明書要求 (結果)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: オンライン証明書の要求の状態ページには、オンライン証明書要求の作成と発行が正常に行われたときに発生した重要な情報が表示されます。 このページでは、証明書を一意に識別する証明書の拇印を提供します。 既定では、この証明書を [Skype for Business Server 証明書の使用状況] に割り当てるチェックボックスがオンになっています。 [完了] をクリックすると、証明書要求の作成手順で定義した目的で、証明書が Skype for Business Server に自動的に割り当てられます。 既定では、証明書が割り当てられる目的は次のとおりです。
ms.openlocfilehash: 02d114ff55360f3e88a866485759510ce5f107c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278022"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="f00d3-107">証明書要求 (結果)</span><span class="sxs-lookup"><span data-stu-id="f00d3-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="f00d3-108">オンライン証明書の**要求の状態**ページには、オンライン証明書要求の作成と発行が正常に行われたときに発生した重要な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f00d3-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="f00d3-109">このページでは、証明書を一意に識別する証明書の拇印を提供します。</span><span class="sxs-lookup"><span data-stu-id="f00d3-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="f00d3-110">既定では、**この証明書を [Skype For Business Server 証明書の使用状況] に割り当てる**チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="f00d3-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="f00d3-111">[**完了**] をクリックすると、証明書要求の作成手順で定義した目的で、証明書が Skype For business Server に自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f00d3-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="f00d3-112">既定では、証明書が割り当てられる目的は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f00d3-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="f00d3-113">相互トランスポート層セキュリティ (MTLS) のサーバーの既定-クライアントおよび他のサーバーへの接続</span><span class="sxs-lookup"><span data-stu-id="f00d3-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="f00d3-114">トランスポート層セキュリティ/セキュアソケットレイヤー (TLS/SSL) 用の内部 Web サービスサイトでの web サービスの内部接続とサーバー接続</span><span class="sxs-lookup"><span data-stu-id="f00d3-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="f00d3-115">TLS/SSL 向けの外部 Web サービスサイトでの Web サービスの外部接続とサーバー接続</span><span class="sxs-lookup"><span data-stu-id="f00d3-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="f00d3-116">[証明書の**詳細の表示**] をクリックして証明書を表示し、証明書のプロパティが意図した内容であることと、証明書を適用してサーバー上で使用できる状態になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f00d3-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="f00d3-117">[**完了**] をクリックして、オンライン証明書要求の処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="f00d3-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="f00d3-118">このチェックボックスをオンにした場合、[**この証明書を Skype For Business Server の証明書の使用状況] に割り当てる**と、証明書が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f00d3-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="f00d3-119">このチェックボックスをオフにした場合は、別の手順で証明書を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f00d3-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f00d3-120">発行証明機関 (CA) のルート証明書が、コンピューターの信頼されたルート証明機関ストアに含まれていない場合、または中間 CA 証明書が適切なストアに存在しない場合は、次の図に示すように概要の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f00d3-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="f00d3-121">証明書を割り当てるオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="f00d3-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="f00d3-122">証明書の割り当て処理を完了するには、発行 CA のルート証明書と中間 CA の証明書をインポートし、メインの証明書ウィザードのページで [**割り当て**] をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f00d3-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  


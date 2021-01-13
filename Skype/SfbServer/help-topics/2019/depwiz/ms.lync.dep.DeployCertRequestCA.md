---
title: 証明書要求 (証明機関)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: '[証明機関 (CA) の選択] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う際に、次の 2 つのオプションが表示されます。'
ms.openlocfilehash: 8744471569c76e8f8196cda41ca398c48205fea8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830367"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="9f9de-103">証明書要求 (証明機関)</span><span class="sxs-lookup"><span data-stu-id="9f9de-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="9f9de-104">[**証明機関 (CA) の選択**] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う際に、次の 2 つのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f9de-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="9f9de-105">環境で検出された一覧から CA を選択する。</span><span class="sxs-lookup"><span data-stu-id="9f9de-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="9f9de-106">別の証明機関を指定する。</span><span class="sxs-lookup"><span data-stu-id="9f9de-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="9f9de-107">最初のオプションを選択すると、環境内で検出された Windows Server ベースのすべての証明機関を含むドロップダウン リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f9de-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="9f9de-108">証明書に適切な証明機関を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9de-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="9f9de-109">どの CA を選択するのかを把握するために、CA 管理者に問い合わせることが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f9de-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="9f9de-p102">2 番目のオプションを選択した場合、証明書に使用する証明機関の完全修飾ドメイン名 (FQDN) および CA インスタンスを入力します。このオプションは、使用する CA が Windows Server ベースの CA ではないが、Windows Server ベースの CA でも機能する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="9f9de-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9f9de-112">証明書要求を適切に行うために必要なグループ メンバーシップを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f9de-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="9f9de-113">通常、証明機関には、サーバーに Skype for Business Server をインストールするための要件とは異なるアクセス許可要件があります。</span><span class="sxs-lookup"><span data-stu-id="9f9de-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="9f9de-114">証明書を要求するための要件について、CA 管理者に確認します。</span><span class="sxs-lookup"><span data-stu-id="9f9de-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  


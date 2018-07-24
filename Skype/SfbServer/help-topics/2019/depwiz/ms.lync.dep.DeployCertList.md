---
title: 証明書のリスト
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: 証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。[次へ] をクリックして続行します。
ms.openlocfilehash: 62dcc2abfde1d2216288b8137a9ab2a2448d5404
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987480"
---
# <a name="certificate-list"></a><span data-ttu-id="e8d93-104">証明書のリスト</span><span class="sxs-lookup"><span data-stu-id="e8d93-104">Certificate List</span></span>
 
<span data-ttu-id="e8d93-p102">証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="e8d93-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="e8d93-p103">[**ローカル証明書ストアから証明書を選びます**] ウィンドウに選択対象として表示される証明書は、必要な証明書使用法に割り当てることができる有効な証明書です。選択する証明書が正しい証明書かどうかは、[**証明書の詳細の表示**] をクリックして確認できます。[**詳細**] タブでは、その証明書で構成されているサブジェクト名とサブジェクトの別名の指定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e8d93-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8d93-p104">選択ウィンドウの一覧に証明書が何も表示されない可能性もあります。そのような場合の一般的な原因は、信頼されたルート証明書または中間証明機関の証明書が目的のサーバーにインストールされていないため、証明書を検証できず、したがって証明書によって作成された証明機関までの信頼チェーンを保持できないことです。この問題を解決するには、ルート証明機関 (CA) 証明書、すべての中間 CA 証明書、および発行 CA 証明書を通常含んでいる、証明書チェーンを要求してインポートします。</span><span class="sxs-lookup"><span data-stu-id="e8d93-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  


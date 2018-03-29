---
title: 証明書のリスト
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。 [次へ] をクリックします。
ms.openlocfilehash: 268d2215aa0a56bc8c86243d99b345831b8d42d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-list"></a><span data-ttu-id="f3bb5-104">証明書のリスト</span><span class="sxs-lookup"><span data-stu-id="f3bb5-104">Certificate List</span></span>
 
<span data-ttu-id="f3bb5-p102">証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f3bb5-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="f3bb5-p103">[**ローカル証明書ストアから証明書を選びます**] ウィンドウに選択対象として表示される証明書は、必要な証明書使用法に割り当てることができる有効な証明書です。選択する証明書が正しい証明書かどうかは、[**証明書の詳細の表示**] をクリックして確認できます。[**詳細**] タブでは、その証明書で構成されているサブジェクト名とサブジェクトの別名の指定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3bb5-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f3bb5-p104">選択ウィンドウの一覧に証明書が何も表示されない可能性もあります。そのような場合の一般的な原因は、信頼されたルート証明書または中間証明機関の証明書が目的のサーバーにインストールされていないため、証明書を検証できず、したがって証明書によって作成された証明機関までの信頼チェーンを保持できないことです。この問題を解決するには、ルート証明機関 (CA) 証明書、すべての中間 CA 証明書、および発行 CA 証明書を通常含んでいる、証明書チェーンを要求してインポートします。</span><span class="sxs-lookup"><span data-stu-id="f3bb5-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  


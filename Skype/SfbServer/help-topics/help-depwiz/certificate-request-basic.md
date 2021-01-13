---
title: 証明書要求 (基本)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: '[名前とセキュリティの設定] ページには、分名を定義するテキスト ボックス、プライベート キーと公開キーのペアのビット長のドロップダウン リスト、および証明書のプライベート キーをエクスポート可能としてマークできるチェック ボックスが表示されます。'
ms.openlocfilehash: f0d0339a483056276d400654f897b898b002cf03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805347"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="e4786-103">証明書要求 (基本)</span><span class="sxs-lookup"><span data-stu-id="e4786-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="e4786-104">[**名前** とセキュリティの設定] ページには、分名を定義するテキスト ボックス、プライベート キーと公開キーのペアのビット長のドロップダウン リスト、および証明書のプライベート キーをエクスポート可能としてマークできるチェック ボックスが用意 **されています。**</span><span class="sxs-lookup"><span data-stu-id="e4786-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="e4786-105">フレンドリ名は、証明書を参照した人が証明書を簡単に識別できるようにするためのわかりやすいシンプルな名前です。</span><span class="sxs-lookup"><span data-stu-id="e4786-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="e4786-106">秘密キーと公開キーの組のビット長は、1024、2048、または 4096 から選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4786-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="e4786-107">[証明書のプライベート キーをエクスポート可能としてマークする] チェック ボックスをオンにすると、証明書とプライベート キーをエクスポートして別のコンピューターまたはサーバーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="e4786-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="e4786-108">これが必要な唯一の時間は、メディア リレー認証サービス (MRAS) 用のエッジ サーバーのプールを作成する場合です。</span><span class="sxs-lookup"><span data-stu-id="e4786-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e4786-109">証明書とキーのペアのセキュリティを維持するために、証明書のプライベート キーをエクスポート可能としてマークするオプションは、本当に必要な場合にのみ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4786-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  


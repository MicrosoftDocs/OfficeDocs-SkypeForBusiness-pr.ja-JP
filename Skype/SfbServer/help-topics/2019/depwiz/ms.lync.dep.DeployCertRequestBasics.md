---
title: 証明書要求 (基本)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: '[名前とセキュリティの設定] ページには、フレンドリ名、秘密キーと公開キーのペアのビット長のためのドロップダウンリスト、証明書の秘密キーをエクスポート可能としてマークするためのチェックボックスが用意されています。'
ms.openlocfilehash: 4759b550c8e6aaa0c09b0ef44a6547ae3722a082
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273774"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="9a011-103">証明書要求 (基本)</span><span class="sxs-lookup"><span data-stu-id="9a011-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="9a011-104">[**名前とセキュリティの設定**] ページには、**フレンドリ名**、秘密キーと公開キーのペアの**ビット長**のためのドロップダウンリスト、**証明書の秘密キーをとしてマークできるチェックボックスが用意されています。エクスポート**可能。</span><span class="sxs-lookup"><span data-stu-id="9a011-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="9a011-105">フレンドリ名は、証明書を参照した人が証明書を簡単に識別できるようにするためのわかりやすいシンプルな名前です。</span><span class="sxs-lookup"><span data-stu-id="9a011-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="9a011-106">秘密キーと公開キーの組のビット長は、1024、2048、または 4096 から選択できます。</span><span class="sxs-lookup"><span data-stu-id="9a011-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="9a011-107">**証明書の秘密キーをエクスポート可能としてマーク**するためのチェックボックスをオンにすると、証明書と秘密キーをエクスポートして、別のコンピューターまたはサーバーに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="9a011-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="9a011-108">これはメディア リレー認証サービス (MRAS) 用にエッジ サーバーのプールを作成する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="9a011-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9a011-109">証明書とキーペアのセキュリティを維持するためには、証明書の秘密キーをエクスポート可能なオプションとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a011-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  


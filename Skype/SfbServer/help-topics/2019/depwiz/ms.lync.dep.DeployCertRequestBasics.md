---
title: 証明書要求 (基本)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: 名前とセキュリティの設定] ページでは、ビット長のプライベートとパブリック キーのペア、および証明書の秘密キーにエクスポート可能のマークを有効にするチェック ボックスのドロップ ダウン リストのフレンドリ名を定義するのにはテキスト ボックスを提供します。
ms.openlocfilehash: abc022cd9126b90fb83244657dfb32ac214a62c8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874802"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="ea239-103">証明書要求 (基本)</span><span class="sxs-lookup"><span data-stu-id="ea239-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="ea239-104">**名前とセキュリティの設定**] ページには、**フレンドリ名**、プライベートとパブリック キーのペア、および**証明書をマークの秘密キーを使用するチェック ボックスの**ビット長**のドロップ ダウン リストを定義するのにはテキスト ボックスが用意されています。エクスポート可能な**です。</span><span class="sxs-lookup"><span data-stu-id="ea239-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="ea239-105">フレンドリ名は、証明書を参照した人が証明書を簡単に識別できるようにするためのわかりやすいシンプルな名前です。</span><span class="sxs-lookup"><span data-stu-id="ea239-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="ea239-106">秘密キーと公開キーの組のビット長は、1024、2048、または 4096 から選択できます。</span><span class="sxs-lookup"><span data-stu-id="ea239-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="ea239-107">**証明書の秘密キーにエクスポート可能のマークを付ける**] チェック ボックスを選択することにより、証明書と秘密キーをエクスポートして別のコンピューターまたはサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea239-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="ea239-108">これはメディア リレー認証サービス (MRAS) 用にエッジ サーバーのプールを作成する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ea239-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ea239-109">証明書とキー ペアのセキュリティを維持するために、選択してくださいマーク秘密キーの証明書のエクスポート可能なオプションとしてどうしても必要な場合にのみ。</span><span class="sxs-lookup"><span data-stu-id="ea239-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  


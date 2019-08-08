---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。 一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用すると、従来の一般的なエリア電話に関連付けられたすべての連絡先オブジェクトが取得され、そのオブジェクトが Skype for Business Server 2019 プールに移動されます。
ms.openlocfilehash: 123f0a73da65e7d661541c6c4bec65481bf12f0c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238026"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="9c71e-106">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="9c71e-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="9c71e-107">一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="9c71e-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="9c71e-108">一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c71e-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="9c71e-109">展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c71e-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="9c71e-110">Skype for Business Server 管理シェルを使用する場合は、まず、従来の共通エリア電話に関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="9c71e-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="9c71e-111">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="9c71e-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="9c71e-112">Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c71e-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="9c71e-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9c71e-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="9c71e-114">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認するには、Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9c71e-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="9c71e-115">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c71e-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    


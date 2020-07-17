---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。 Skype for Business Server 統合コミュニケーション (UC) 機能を提供するために、共通領域電話をコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用して、まず、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752709"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="f0e82-106">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="f0e82-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="f0e82-107">共通領域電話は、ロビー、調理場、または工場の作業場のような、共有ワークスペースまたは共用エリアによく設置されている IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="f0e82-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="f0e82-108">Skype for Business Server 統合コミュニケーション (UC) 機能を提供するために、共通領域電話をコンピューターに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f0e82-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="f0e82-109">展開を Skype for Business Server 2019 に移行した後、従来の共通領域電話に関連付けられている連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0e82-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="f0e82-110">Skype for business Server 管理シェルを使用して、まず、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="f0e82-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="f0e82-111">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="f0e82-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="f0e82-112">Skype for business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0e82-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="f0e82-113">コマンド ラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e82-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="f0e82-114">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認するには、Skype for Business Server 管理シェルから次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f0e82-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="f0e82-115">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0e82-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    


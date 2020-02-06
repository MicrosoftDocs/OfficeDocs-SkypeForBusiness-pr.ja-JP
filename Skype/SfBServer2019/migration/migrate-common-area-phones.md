---
title: 共通領域電話の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。 一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。 展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用すると、従来の一般的なエリア電話に関連付けられたすべての連絡先オブジェクトが取得され、そのオブジェクトが Skype for Business Server 2019 プールに移動されます。
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813565"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="1ce4e-106">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="1ce4e-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="1ce4e-107">一般的なエリア携帯電話は、共通のワークスペースや一般的な領域 (ロビー、台所、工場など) に存在する IP 電話です。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="1ce4e-108">一般的なエリア携帯電話は、Skype for Business Server 統合通信 (UC) 機能を提供するためにコンピューターに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="1ce4e-109">展開を Skype for Business Server 2019 に移行した後は、従来の共通エリア電話に関連付けられた連絡先オブジェクトも移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="1ce4e-110">Skype for Business Server 管理シェルを使用する場合は、まず、従来の共通エリア電話に関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="1ce4e-111">共通領域電話の移行</span><span class="sxs-lookup"><span data-stu-id="1ce4e-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="1ce4e-112">Skype for Business Server 2019 フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="1ce4e-113">コマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="1ce4e-114">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認するには、Skype for Business Server 管理シェルで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="1ce4e-115">すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ce4e-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    


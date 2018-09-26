---
title: 共通領域電話を移行します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。 共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。 ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。 ビジネス サーバー管理シェルの Skype を使用する従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。
ms.openlocfilehash: 6d5adebd4ab1b4cb79d79f4049c7d7456bb07a29
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028027"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="ad74f-106">共通領域電話を移行します。</span><span class="sxs-lookup"><span data-stu-id="ad74f-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="ad74f-107">共通領域電話は、IP 電話のほとんどは、共有ワークスペース、または共通の領域で多くの場合にあるロビー、キッチン、または工場出荷時のフロアのようです。</span><span class="sxs-lookup"><span data-stu-id="ad74f-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="ad74f-108">共通領域電話は、Skype のビジネス サーバーのユニファイド コミュニケーション (UC) の機能を提供するコンピューターに接続する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad74f-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="ad74f-109">ビジネス サーバー 2019 用に展開を Skype に移行した後も従来の共通領域電話に関連付けられている連絡先オブジェクトを移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad74f-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="ad74f-110">Skype ビジネス サーバー管理シェルを使用すると、従来の共通領域電話に関連付けられているすべての連絡先オブジェクトを取得し、ビジネス サーバー 2019 プールの Skype にそれらのオブジェクトを移動します。</span><span class="sxs-lookup"><span data-stu-id="ad74f-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="ad74f-111">共通領域電話を移行します。</span><span class="sxs-lookup"><span data-stu-id="ad74f-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="ad74f-112">ビジネス サーバー 2019 のフロント エンド サーバーの Skype、Skype ビジネス サーバー管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad74f-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="ad74f-113">コマンド ・ ラインから次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ad74f-113">From the command line, type the following:</span></span>
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
  ```

3. <span data-ttu-id="ad74f-114">連絡先のすべてのオブジェクト移動されている、Skype をビジネス サーバー 2019 プールのことを確認するには、ビジネスのサーバー管理シェルの Skype から次のとおり入力します。</span><span class="sxs-lookup"><span data-stu-id="ad74f-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
  ```

    <span data-ttu-id="ad74f-115">連絡先オブジェクトがすべて表示されていることを確認して、Skype のビジネス サーバー 2019 プールに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="ad74f-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    


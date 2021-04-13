---
title: オンプレミスの Skype for Business 環境を廃止する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: オンプレミスの Skype for Business 環境を使用停止する方法について説明します。
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656683"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="ac6de-103">オンプレミスの Skype for Business 環境を廃止する</span><span class="sxs-lookup"><span data-stu-id="ac6de-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="ac6de-104">組織で Skype for Business Server のオンプレミス展開で Teams または Skype for Business Online を使用している場合は、これらの環境をクラウドに完全に移行し、Skype for Business Server のオンプレミス展開を廃止できます。</span><span class="sxs-lookup"><span data-stu-id="ac6de-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="ac6de-105">オンプレミス環境を使用停止する前に、オンプレミス展開と[](configure-hybrid-connectivity.md)Microsoft 365 の間のハイブリッド接続を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac6de-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="ac6de-106">ハイブリッド接続を構成した後、ユーザーをクラウドに移行しながら、会議をオンプレミスから移行し、Skype for Business Server から Teams に連絡先を移行できます。</span><span class="sxs-lookup"><span data-stu-id="ac6de-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="ac6de-107">ハイブリッド接続の構成は、ユーザーをオンプレミスからクラウドに移行し、Teams の完全な機能を確保するために必要な手順です。</span><span class="sxs-lookup"><span data-stu-id="ac6de-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="ac6de-108">オンプレミスからクラウドへの移行を完了し、オンプレミスの Skype for Business Server 環境を使用停止するには、次の順序で次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac6de-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="ac6de-109">**手順 1.**</span><span class="sxs-lookup"><span data-stu-id="ac6de-109">**Step 1.**</span></span> <span data-ttu-id="ac6de-110">[必要なすべてのユーザーをオンプレミスからオンラインに移動します](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6de-110">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="ac6de-111">**手順 2.**</span><span class="sxs-lookup"><span data-stu-id="ac6de-111">**Step 2.**</span></span> <span data-ttu-id="ac6de-112">[ハイブリッド構成を無効にします](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6de-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="ac6de-113">**手順 3.**</span><span class="sxs-lookup"><span data-stu-id="ac6de-113">**Step 3.**</span></span> <span data-ttu-id="ac6de-114">[ハイブリッド アプリケーション エンドポイントをオンプレミスからオンラインに移動します](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6de-114">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="ac6de-115">**手順 4.**</span><span class="sxs-lookup"><span data-stu-id="ac6de-115">**Step 4.**</span></span> <span data-ttu-id="ac6de-116">[オンプレミスの Skype for Business 展開を削除します](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="ac6de-116">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


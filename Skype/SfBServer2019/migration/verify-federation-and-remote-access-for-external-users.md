---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 エッジサーバーへのフェデレーションルートの移行が完了したら、いくつかの機能テストを実行して、フェデレーションが期待どおりに実行されることを確認する必要があります。 外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292173"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="16a95-104">外部ユーザーのフェデレーションとリモート アクセスの確認</span><span class="sxs-lookup"><span data-stu-id="16a95-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="16a95-105">Skype for Business Server 2019 エッジサーバーへのフェデレーションルートの移行が完了したら、いくつかの機能テストを実行して、フェデレーションが期待どおりに実行されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a95-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="16a95-106">外部ユーザーアクセスのテストには、次のいずれか、またはすべてを含む、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="16a95-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="16a95-107">外部ユーザーと外部アクセスの接続性をテストする</span><span class="sxs-lookup"><span data-stu-id="16a95-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="16a95-108">少なくとも1つのフェデレーションドメイン、Skype for Business Server 2019 の内部ユーザー、レガシインストールのユーザー。</span><span class="sxs-lookup"><span data-stu-id="16a95-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="16a95-109">インスタントメッセージング (IM)、プレゼンス、音声/ビデオ (A/V)、デスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="16a95-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="16a95-110">組織がサポートしている各パブリック IM サービスプロバイダー (およびプロビジョニングが完了した状態) のユーザーは、Skype for Business Server 2019 およびレガシインストールのユーザーとの通信を行います。</span><span class="sxs-lookup"><span data-stu-id="16a95-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="16a95-111">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="16a95-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="16a95-112">リモートユーザーアクセスを使用してホストされている (Lync server/skype for business を、イントラネットの外部から、VPN を使わずに)、レガシインストールのユーザー2019に対してホストされているユーザー。</span><span class="sxs-lookup"><span data-stu-id="16a95-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="16a95-113">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="16a95-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="16a95-114">Skype for business server 2019 でホストされているユーザー (リモートユーザーアクセスを使っていますが、skype for business server 2019 のユーザーと、レガシインストールのユーザーによる VPN 2019 を使用していない場合)。</span><span class="sxs-lookup"><span data-stu-id="16a95-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="16a95-115">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="16a95-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


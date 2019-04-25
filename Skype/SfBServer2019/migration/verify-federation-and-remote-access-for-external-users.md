---
title: 外部ユーザーのフェデレーションとリモート アクセスの確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。 外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231351"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="75620-104">外部ユーザーのフェデレーションとリモート アクセスの確認</span><span class="sxs-lookup"><span data-stu-id="75620-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="75620-105">ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="75620-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="75620-106">外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="75620-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="75620-107">外部のユーザーと外部アクセスの接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="75620-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="75620-108">少なくとも 1 つのフェデレーション ドメイン、内部のビジネス サーバー 2019、Skype のユーザーと従来のユーザーからのユーザーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="75620-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75620-109">インスタント メッセージング (IM)、プレゼンス、オーディオとビデオをテストする (A/V)、デスクトップの共有とします。</span><span class="sxs-lookup"><span data-stu-id="75620-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="75620-110">組織をサポートするなど準備が完了した対象の各パブリック IM サービス プロバイダーのユーザー ビジネス サーバー 2019 および従来のインストール時にユーザーの Skype 上のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="75620-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="75620-111">匿名ユーザーが会議に参加することであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="75620-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="75620-112">従来でホストされているユーザーは、リモート ユーザー アクセスを使用してをインストール (i のログ %ndns Lync Server と Skype からビジネスの VPN のせずにイントラネットの外部) のビジネス サーバー 2019、Skype のユーザーと従来のインストール時にユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="75620-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75620-113">テスト IM、プレゼンス、A/V、およびデスクトップの共有します。</span><span class="sxs-lookup"><span data-stu-id="75620-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="75620-114">ビジネス サーバー 2019、Skype のユーザーと従来のユーザーとリモート ユーザー アクセス (ログ Skype にからのビジネス サーバー 2019 の VPN のせずにイントラネットの外部) を使用して、ビジネス サーバー 2019 の Skype 上でホストされているユーザーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="75620-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75620-115">テスト IM、プレゼンス、A/V、およびデスクトップの共有します。</span><span class="sxs-lookup"><span data-stu-id="75620-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


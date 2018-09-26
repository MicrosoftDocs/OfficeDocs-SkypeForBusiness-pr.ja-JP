---
title: フェデレーションと外部ユーザー用のリモート アクセスを確認します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。 外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。
ms.openlocfilehash: ce0e2dd6ee7d4fb605f844d7dfb26b3f9d13bf14
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027236"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="a0f09-104">フェデレーションと外部ユーザー用のリモート アクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0f09-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="a0f09-105">ビジネス 2019 エッジ サーバーのフェデレーション ルート、Skype を移行した後は、フェデレーションが期待どおりに実行されることを確認するのにはいくつかの機能テストを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0f09-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="a0f09-106">外部ユーザー アクセスのテストには、次の一部またはすべてを含む、組織をサポートする外部ユーザーの種類を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0f09-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="a0f09-107">外部のユーザーと外部アクセスの接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="a0f09-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="a0f09-108">少なくとも 1 つのフェデレーション ドメイン、内部のビジネス サーバー 2019、Skype のユーザーと従来のユーザーからのユーザーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a0f09-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a0f09-109">インスタント メッセージング (IM)、プレゼンス、オーディオとビデオをテストする (A/V)、デスクトップの共有とします。</span><span class="sxs-lookup"><span data-stu-id="a0f09-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="a0f09-110">組織をサポートするなど準備が完了した対象の各パブリック IM サービス プロバイダーのユーザー ビジネス サーバー 2019 および従来のインストール時にユーザーの Skype 上のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="a0f09-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="a0f09-111">匿名ユーザーが会議に参加することであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0f09-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="a0f09-112">従来でホストされているユーザーは、リモート ユーザー アクセスを使用してをインストール (i のログ %ndns Lync Server と Skype からビジネスの VPN のせずにイントラネットの外部) のビジネス サーバー 2019、Skype のユーザーと従来のインストール時にユーザーにします。</span><span class="sxs-lookup"><span data-stu-id="a0f09-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a0f09-113">テスト IM、プレゼンス、A/V、およびデスクトップの共有します。</span><span class="sxs-lookup"><span data-stu-id="a0f09-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="a0f09-114">ビジネス サーバー 2019、Skype のユーザーと従来のユーザーとリモート ユーザー アクセス (ログ Skype にからのビジネス サーバー 2019 の VPN のせずにイントラネットの外部) を使用して、ビジネス サーバー 2019 の Skype 上でホストされているユーザーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a0f09-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a0f09-115">テスト IM、プレゼンス、A/V、およびデスクトップの共有します。</span><span class="sxs-lookup"><span data-stu-id="a0f09-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


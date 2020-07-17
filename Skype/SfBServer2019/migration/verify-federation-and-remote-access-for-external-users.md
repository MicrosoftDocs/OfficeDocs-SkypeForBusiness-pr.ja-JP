---
title: 外部ユーザーのフェデレーションとリモート アクセスを確認する
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
description: フェデレーションルートを Skype for Business Server 2019 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。 外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751669"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="98a55-104">外部ユーザーのフェデレーションとリモート アクセスを確認する</span><span class="sxs-lookup"><span data-stu-id="98a55-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="98a55-105">フェデレーションルートを Skype for Business Server 2019 エッジサーバーに移行した後、機能テストを実行して、フェデレーションが期待どおりに動作することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98a55-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="98a55-106">外部ユーザー アクセスのテストには、次のいずれかまたはすべてなど、組織がサポートしている各種類の外部ユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="98a55-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="98a55-107">外部ユーザーの接続と外部アクセスをテストする</span><span class="sxs-lookup"><span data-stu-id="98a55-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="98a55-108">少なくとも1つのフェデレーションドメイン、Skype for Business Server 2019 上の内部ユーザー、および従来のインストールのユーザー。</span><span class="sxs-lookup"><span data-stu-id="98a55-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="98a55-109">インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="98a55-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="98a55-110">組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーは、Skype for Business Server 2019 上のユーザーと従来のインストールのユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="98a55-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="98a55-111">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="98a55-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="98a55-112">従来のインストールで、リモートユーザーアクセス (Lync Server/Skype for Business の外部から VPN を使用しない) を使用してホストされているユーザーが、Skype for Business Server 2019 上のユーザーと、レガシインストール上のユーザーを使用しています。</span><span class="sxs-lookup"><span data-stu-id="98a55-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="98a55-113">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="98a55-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="98a55-114">Skype for business Server 2019 でホストされているユーザー (リモートユーザーアクセスを使用) (skype for business Server 2019 から VPN を使用しない)、Skype for Business Server 2019 のユーザー、およびレガシインストールのユーザーに対してログインします。</span><span class="sxs-lookup"><span data-stu-id="98a55-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="98a55-115">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="98a55-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


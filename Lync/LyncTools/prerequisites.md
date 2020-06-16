---
title: 前提条件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d8f0ee6a50d40f938a9f2c6f731b0a4afa647ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="a835f-102">前提条件</span><span class="sxs-lookup"><span data-stu-id="a835f-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a835f-103">_**トピックの最終更新日:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="a835f-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="a835f-104">Lync Server 2013 ストレスおよびパフォーマンスツールを実行するには、さまざまなハードウェア、ソフトウェア、およびシステム構成の要件があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="a835f-105">クライアントハードウェアの要件</span><span class="sxs-lookup"><span data-stu-id="a835f-105">Client Hardware Requirements</span></span>

<span data-ttu-id="a835f-106">Lync server 2013 のストレスおよびパフォーマンスツールを Lync Server 2013 展開で実行するには、負荷をシミュレートするすべての4500ユーザーに対して、次の最小ハードウェア要件を満たしている少なくとも1つの専用コンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a835f-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="a835f-107">1ギガビットのネットワークアダプター</span><span class="sxs-lookup"><span data-stu-id="a835f-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="a835f-108">8 GB の ram</span><span class="sxs-lookup"><span data-stu-id="a835f-108">8-GB ram</span></span>

  - <span data-ttu-id="a835f-109">2つのデュアルコア中央処理装置 (Cpu)</span><span class="sxs-lookup"><span data-stu-id="a835f-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="a835f-110">クライアントソフトウェアの要件</span><span class="sxs-lookup"><span data-stu-id="a835f-110">Client Software Requirements</span></span>

<span data-ttu-id="a835f-111">Lync server 2013 のストレスおよびパフォーマンスツールを Lync Server 2013 展開で実行するために、サポートされているオペレーティングシステムは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a835f-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="a835f-112">Windows Server 2012 オペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="a835f-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="a835f-113">Windows Server 2008 オペレーティングシステム (64 ビット版)</span><span class="sxs-lookup"><span data-stu-id="a835f-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="a835f-114">クライアントコンピューターは、次のソフトウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="a835f-115">[Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)ランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="a835f-116">Windows Server 2008/Windows Server 2012 では、デスクトップ環境機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="a835f-117">[Microsoft Visual C++ 2012 再頒布可能パッケージ](https://go.microsoft.com/fwlink/?linkid=143216)(x64) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="a835f-118">完全に構成された Lync Server 2013 の展開。</span><span class="sxs-lookup"><span data-stu-id="a835f-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a835f-119">Microsoft 統合コミュニケーション管理 API (UCMA) 4.0 ライブラリはインストールパッケージに含まれているため、UCMA は必要ではなく、クライアントコンピューターにインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a835f-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="a835f-120">構成要件</span><span class="sxs-lookup"><span data-stu-id="a835f-120">Configuration Requirements</span></span>

<span data-ttu-id="a835f-121">Lync Server 2013 ストレスおよびパフォーマンスツールを実行するコンピューターは、次の要件に従って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="a835f-122">ドメインまたはローカルの管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="a835f-123">Lync server 2013 コンポーネントを実行しているコンピューターで lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool.exe) を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a835f-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="a835f-124">ユーザーアカウントが存在するフロントエンドサーバーまたは Standard Edition サーバーで Lync Server 2013 ユーザー作成ツール (UserProvisioningTool.exe) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="a835f-125">ツールを複数回実行する場合、Microsoft ユニファイドコミュニケーションが有効になっている各ユーザーは、一意の電話番号を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="a835f-126">ページファイルのサイズは、システムで管理されているか、システムの RAM の容量の少なくとも1.5 倍になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a835f-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


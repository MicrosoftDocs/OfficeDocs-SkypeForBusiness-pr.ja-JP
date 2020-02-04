---
title: 'Lync Server 2013: トポロジテストの問題'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0492f53692230bf02b3b66d91ba7fdf14b01c23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="4e261-102">Lync Server 2013 でのトポロジテストの問題</span><span class="sxs-lookup"><span data-stu-id="4e261-102">Issues with the topology test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e261-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4e261-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4e261-104">ベストプラクティスアナライザーは、**テスト-CsTopology**コマンドレットと同様に、Lync Server 2013 がグローバルレベルで正常に機能しているかどうかを確認するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e261-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="4e261-105">既定では、コマンドレットなどのベストプラクティスアナライザーは、Lync Server 2013 インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスとユニバーサル用に適切なユーザー権限と権限が設定されていることを確認します。Lync Server 2013 をインストールしたときに作成されるセキュリティグループ。</span><span class="sxs-lookup"><span data-stu-id="4e261-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="4e261-106">Lync Server 全体としての有効性を確認するだけでなく、**テスト用**に、特定のサービスの有効性も確認します。</span><span class="sxs-lookup"><span data-stu-id="4e261-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="4e261-107">コマンドレットを使用して特定のサービスをテストする方法について詳しくは、「Lync Server 管理シェルドキュメント」の「[テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology)使い方」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e261-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="4e261-108">以下の情報を参考にして、トポロジの問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="4e261-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e261-109">ベストプラクティスアナライザーは、エッジサーバーの構成と、ファイアウォールの設定やアクセス許可を含む、関連する境界ネットワーク設定に応じて、エッジサーバーにアクセスしてスキャンできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-109">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers.</span></span> <span data-ttu-id="4e261-110">スキャンにエッジサーバーが含まれていて、エッジサーバーへのアクセスに問題があるという報告があった場合は、[<STRONG>エッジサーバー</STRONG> ] チェックボックスをオフにし、もう一度スキャンを実行して、問題がレポートに表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="4e261-110">If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="4e261-111">トポロジの問題を解決する</span><span class="sxs-lookup"><span data-stu-id="4e261-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="4e261-112">トポロジテストでトポロジの問題が検出された場合、この問題は、トポロジを公開または有効にしたときに発生した問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="4e261-113">トポロジに変更を加えた場合、変更は、公開されていて有効になっている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="4e261-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="4e261-114">トポロジを変更するには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="4e261-115">変更を加えた後は、トポロジビルダーを使用して、変更を発行して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e261-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="4e261-116">変更を公開すると、新しい情報 (たとえば、新しいサイトまたは新しいサーバーの役割) が中央管理ストアに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4e261-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="4e261-117">ただし、これらの新規 (または新しく更新された) オブジェクトは、すぐにトポロジに参加することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e261-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="4e261-118">更新されたトポロジを有効にした場合にのみ、オブジェクトはトポロジに参加します。</span><span class="sxs-lookup"><span data-stu-id="4e261-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="4e261-119">トポロジビルダーで [発行] オプションを選択した場合、次の手順のいずれかが行われます。変更は公開されます (つまり、中央管理ストアに作成されます)。次に、新しいトポロジが有効になります。</span><span class="sxs-lookup"><span data-stu-id="4e261-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="4e261-120">既定では、RTCUniversalServerAdmins グループのメンバーは、 **Publish/cstopology**コマンドレットと**Enable-cstopology**コマンドレットを実行することを許可されています。</span><span class="sxs-lookup"><span data-stu-id="4e261-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="4e261-121">ただし、セットアップのアクセス許可が委任されていない場合は、ドメイン管理者としてログオンして**発行-CsTopology**方法で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="4e261-122">RTCUniversalServerAdmins を実際に使用する権利を与えられるようにする**には、** Lync Server サービスを実行しているコンピューターが含まれているすべての Active Directory コンテナーに対して、**グラント setuppermission**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="4e261-123">RTCUniversalServerAdmins を有効にするには、 **Enable-CsTopology**コマンドレットを使用する権利を付与するために、Lync Server サービスを実行しているコンピューターが含まれているすべての Active Directory ドメインサービスコンテナーに対して、 **Set-cssetuppermission**コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e261-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="4e261-124">これは、トポロジビルダーを使用してトポロジを有効化および公開するために適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4e261-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="4e261-125">**Set-CsSetupPermission**を使用してアクセス許可を委任していない場合は、トポロジビルダーを介してトポロジを有効にして発行できるのは、ドメイン管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="4e261-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


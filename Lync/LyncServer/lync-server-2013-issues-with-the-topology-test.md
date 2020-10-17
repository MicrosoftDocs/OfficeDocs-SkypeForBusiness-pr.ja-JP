---
title: 'Lync Server 2013: トポロジテストに関する問題'
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
ms.openlocfilehash: 7095e539ec8e9cc832b4ce69f2e347bfcea38ccc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514034"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a><span data-ttu-id="60cc5-102">Lync Server 2013 のトポロジテストに関する問題</span><span class="sxs-lookup"><span data-stu-id="60cc5-102">Issues with the topology test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60cc5-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="60cc5-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="60cc5-104">**Test-CsTopology**コマンドレットと同様に、ベストプラクティスアナライザーは Lync Server 2013 がグローバルレベルで正常に機能していることを確認する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="60cc5-104">Like the **Test-CsTopology** cmdlet, Best Practice Analyzer provides a way for you to verify that Lync Server 2013 is functioning correctly at a global level.</span></span> <span data-ttu-id="60cc5-105">既定では、コマンドレットなどのベストプラクティスアナライザーは、Lync Server 2013 インフラストラクチャ全体をチェックし、必要なサービスが実行されていること、およびこれらのサービスに対して適切なユーザー権限とアクセス許可が設定されていること、および Lync Server 2013 のインストール時に作成されたユニバーサルセキュリティグループに対して適切なユーザー権限とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="60cc5-105">By default, Best Practice Analyzer, like the cmdlet, checks your entire Lync Server 2013 infrastructure, verifying that the required services are running, and that the appropriate user rights and permissions have been set for these services and for the universal security groups created when you install Lync Server 2013.</span></span>

<span data-ttu-id="60cc5-106">Lync Server 全体としての有効性を検証するだけでなく、特定のサービスの **有効性も確認** します。</span><span class="sxs-lookup"><span data-stu-id="60cc5-106">In addition to verifying the validity of Lync Server as a whole, **Test-CsTopology** also checks the validity of a specific service.</span></span> <span data-ttu-id="60cc5-107">コマンドレットを使用して特定のサービスをテストする方法の詳細については、「Lync Server Management Shell」のドキュメントの「 [テスト-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) 方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60cc5-107">For details about using the cmdlet to test specific services, see [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="60cc5-108">トポロジの問題の解決については、以下の情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="60cc5-108">Use the following information to help resolve issues with your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60cc5-p103">エッジ サーバーの構成および関連する境界ネットワークの設定 (ファイアウォールの設定とアクセス許可など) によっては、ベスト プラクティス アナライザーがエッジ サーバーにアクセスしてスキャンできない場合があります。エッジ サーバーがスキャンに含まれていて、エッジ サーバーへのアクセスに問題があることが報告される場合は、[<STRONG>エッジ サーバー</STRONG>] チェック ボックスをオフにしてスキャンを再び実行し、問題がレポートに表示されないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="60cc5-p103">Depending on the configuration of your Edge Servers and any related perimeter network settings, including firewall settings and permissions, Best Practices Analyzer might not be able to access and scan your Edge Servers. If you include Edge Servers in your scan and the reports indicate that there is an issue accessing Edge Servers, clear the <STRONG>Edge Servers</STRONG> check box and run the scan again to prevent the issue from showing up in reports.</span></span>



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a><span data-ttu-id="60cc5-111">トポロジの問題の解決</span><span class="sxs-lookup"><span data-stu-id="60cc5-111">Resolving Issues with Your Topology</span></span>

<span data-ttu-id="60cc5-112">トポロジ テストでトポロジに問題が見つかった場合、トポロジを公開または有効化するときに発生した問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-112">If the topology test found issues with your topology, these issues are probably caused by issues that occurred when you published or enabled your topology.</span></span>

<span data-ttu-id="60cc5-113">トポロジを変更すると、公開して有効にするまで、その変更は反映されません。</span><span class="sxs-lookup"><span data-stu-id="60cc5-113">When you make changes to your topology, the changes take effect only when they have been both published and enabled.</span></span> <span data-ttu-id="60cc5-114">トポロジの変更を行うには、トポロジビルダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-114">You must use Topology Builder to make topology changes.</span></span> <span data-ttu-id="60cc5-115">変更した後は、トポロジビルダーを使用して、これらの変更を公開して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="60cc5-115">After you make changes, you can then publish and enable those changes by using Topology Builder.</span></span>

<span data-ttu-id="60cc5-116">変更を公開すると、新しい情報 (たとえば、新しいサイトまたは新しいサーバーの役割) が中央管理ストアに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="60cc5-116">When you publish the changes, the new information (for example, a new site or a new server role) is written to the Central Management store.</span></span> <span data-ttu-id="60cc5-117">ただし、これらの新しい (または新しく変更された) オブジェクトは、すぐにはトポロジに参加しません。</span><span class="sxs-lookup"><span data-stu-id="60cc5-117">However, these new (or the newly modified) objects do not immediately join your topology.</span></span> <span data-ttu-id="60cc5-118">オブジェクトは、更新されたトポロジを有効にした場合にのみ、トポロジに参加します。</span><span class="sxs-lookup"><span data-stu-id="60cc5-118">Objects join your topology only when you enable the updated topology.</span></span> <span data-ttu-id="60cc5-119">トポロジビルダーで [発行] オプションを選択した場合、次の両方の手順が実行されます。変更が発行されます (つまり、中央管理ストアに書き込まれます)。その後、新しいトポロジが有効になります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-119">If you select the Publish option in Topology Builder both of these steps occur: the changes are published (that is, they are written to the Central Management store) and then the new topology is enabled.</span></span>

<span data-ttu-id="60cc5-120">既定では、RTCUniversalServerAdmins グループのメンバーは、**Publish-CsTopology** コマンドレットおよび **Enable-CsTopology** コマンドレットの実行を許可されてます。</span><span class="sxs-lookup"><span data-stu-id="60cc5-120">By default, members of the RTCUniversalServerAdmins group are authorized to run the **Publish-CsTopology** cmdlet and the **Enable-CsTopology** cmdlet.</span></span> <span data-ttu-id="60cc5-121">ただし、セットアップ アクセス許可が委任されていない場合は、ドメイン管理者としてログオンし、**Publish-CsTopology** を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-121">However, if setup permissions have not been delegated, you must be logged on as a domain administrator to run **Publish-CsTopology**.</span></span> <span data-ttu-id="60cc5-122">RTCUniversalServerAdmins コマンドレットを実際に使用する権限を付与する **には、** Lync Server サービスを実行しているコンピューターが含まれるすべての Active Directory コンテナーで、 **Grant-cssetuppermission** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-122">To give RTCUniversalServerAdmins the right to actually use the **Publish-CsTopology** cmdlet, you must run the **Grant-CsSetupPermission** cmdlet on every Active Directory container that contains computers running Lync Server services.</span></span> <span data-ttu-id="60cc5-123">RTCUniversalServerAdmins **コマンドレットを** 使用する権限を付与するには、Lync Server サービスを実行しているコンピューターが含まれるすべての Active Directory ドメインサービスコンテナーに対し **て、コマンドレットを** 実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-123">To give RTCUniversalServerAdmins the right to use the **Enable-CsTopology** cmdlet, you must run the **Set-CsSetupPermission** cmdlet against every Active Directory Domain Services container that contains computers running Lync Server services.</span></span> <span data-ttu-id="60cc5-124">このことは、トポロジビルダーを使用したトポロジの有効化と公開に適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60cc5-124">Note that this applies to enabling and publishing a topology by using Topology Builder.</span></span> <span data-ttu-id="60cc5-125">**Set-CsSetupPermission**を使用してアクセス許可を委任していない場合は、トポロジビルダーを使用してトポロジを有効にして公開できるのはドメイン管理者のみになります。</span><span class="sxs-lookup"><span data-stu-id="60cc5-125">If you have not delegated permissions by using **Set-CsSetupPermission**, only a domain administrator can enable and publish a topology through Topology Builder.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


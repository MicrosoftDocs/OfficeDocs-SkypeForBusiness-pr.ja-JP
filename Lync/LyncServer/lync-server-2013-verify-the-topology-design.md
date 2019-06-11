---
title: 'Lync Server 2013: トポロジ設計の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbe262033699e46c77897652cf48969d46b7817f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="715e9-102">Lync Server 2013 でのトポロジ設計の確認</span><span class="sxs-lookup"><span data-stu-id="715e9-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="715e9-103">_**最終更新日:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="715e9-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="715e9-104">トポロジビルダーは、トポロジを自動的に確認します。</span><span class="sxs-lookup"><span data-stu-id="715e9-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="715e9-105">トポロジエラーは検証エラーとして識別され、サーバーの役割の横に表示される検証エラーアイコンによって示されます。</span><span class="sxs-lookup"><span data-stu-id="715e9-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="715e9-106">トポロジが配置のトポロジを正しく表すことも確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="715e9-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="715e9-107">公開前にトポロジを確認するには</span><span class="sxs-lookup"><span data-stu-id="715e9-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="715e9-108">すべての簡易 URL が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="715e9-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="715e9-109">SQL Server ベースのサーバーがオンラインになっていることを確認します。また、トポロジ ビルダーがインストールされているコンピューターでこのサーバーが使用できることを確認します。必要なファイアウォール規則などを確認してください。</span><span class="sxs-lookup"><span data-stu-id="715e9-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="715e9-110">ファイル共有が使用可能であり、適切なアクセス許可が定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="715e9-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="715e9-111">トポロジで、展開要件を満たす正しいサーバーの役割が定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="715e9-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="715e9-112">サーバーが Active Directory ドメインサービスに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="715e9-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="715e9-113">この問題は、サーバーをドメインに参加している場合に自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="715e9-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="715e9-114">トポロジの検証が完了して検証エラーがないことが確認できたら、トポロジの公開の準備に移ります。</span><span class="sxs-lookup"><span data-stu-id="715e9-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="715e9-115">検証エラーがある場合は、トポロジを公開する前に修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="715e9-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="715e9-116">トポロジの公開について詳しくは、「 [Lync Server 2013 でトポロジを発行する](lync-server-2013-publish-the-topology.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="715e9-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


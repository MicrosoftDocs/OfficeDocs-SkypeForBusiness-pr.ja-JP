---
title: 音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd34109b08a9436d4e2ab1fc7664d843fe9f6df5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="95a80-102">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</span><span class="sxs-lookup"><span data-stu-id="95a80-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a80-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="95a80-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="95a80-p101">音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。 音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。 PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。 つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="95a80-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="95a80-108">新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="95a80-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="95a80-109"><EM></EM>ユーザー スコープを使用して音声ポリシーを作成し、それを個々のユーザーまたはグループに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="95a80-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="95a80-110">これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95a80-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="95a80-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="95a80-111">In This Section</span></span>

  - [<span data-ttu-id="95a80-112">Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="95a80-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="95a80-113">Lync Server 2013 での PSTN 使用法レコードの表示</span><span class="sxs-lookup"><span data-stu-id="95a80-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="95a80-114">Lync Server 2013 での発信通話の音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="95a80-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="95a80-115">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="95a80-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="95a80-116">Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する</span><span class="sxs-lookup"><span data-stu-id="95a80-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="95a80-117">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="95a80-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


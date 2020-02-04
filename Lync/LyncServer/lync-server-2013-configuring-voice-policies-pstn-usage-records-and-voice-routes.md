---
title: 音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する
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
ms.openlocfilehash: e3a87063503d373c8ef318633c5113624fef00b7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="67b10-102">Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成</span><span class="sxs-lookup"><span data-stu-id="67b10-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67b10-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="67b10-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="67b10-p101">音声ポリシー、PSTN 使用法レコード、およびボイス ルートは、一体的に関わり合っています。音声ポリシーは、一連の通話機能を選択し、PSTN 使用法レコードのセット (音声ポリシーを割り当てられるユーザーまたはグループを対象に、承認される権限を指定します) にポリシーを割り当てることで、構成します。PSTN 使用法レコードは、ボイス ルートにも割り当てられます。これにより、ルートとこの PSTN 使用法レコードの使用を許可されたユーザーが照合されます。つまり、ユーザーはルートと一致する PSTN 使用法レコードが割り当てられている場合のみ、そのルートに電話をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="67b10-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="67b10-108">新しいエンタープライズ VoIP を展開する場合の推奨ワークフローは、最初に該当する PSTN 使用法レコードを含む音声ポリシーを構成し、次に、該当するルートを各 PSTN 使用法レコードに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="67b10-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="67b10-109"><EM>ユーザー スコープ</EM>を使用して音声ポリシーを作成し、それを個々のユーザーまたはグループに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="67b10-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="67b10-110">これらの各タスクを実行するための詳細ステップについては、このセクションの手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67b10-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="67b10-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="67b10-111">In This Section</span></span>

  - [<span data-ttu-id="67b10-112">Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成</span><span class="sxs-lookup"><span data-stu-id="67b10-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="67b10-113">Lync Server 2013 での PSTN 使用状況レコードの表示</span><span class="sxs-lookup"><span data-stu-id="67b10-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="67b10-114">Lync Server 2013 での発信通話用のボイス ルートの構成</span><span class="sxs-lookup"><span data-stu-id="67b10-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="67b10-115">Lync Server 2013 での音声ルーティング構成のエクスポートとインポート</span><span class="sxs-lookup"><span data-stu-id="67b10-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="67b10-116">Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する</span><span class="sxs-lookup"><span data-stu-id="67b10-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="67b10-117">Lync Server 2013 での音声ルーティングのテスト</span><span class="sxs-lookup"><span data-stu-id="67b10-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


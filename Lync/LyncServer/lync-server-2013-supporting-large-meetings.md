---
title: 'Lync Server 2013: 大規模な会議のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="7c57a-102">Lync Server 2013 を使用した大規模な会議のサポート</span><span class="sxs-lookup"><span data-stu-id="7c57a-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c57a-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7c57a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7c57a-104">大規模な会議は、前のセクションで説明したテストモデルに従っていないため、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="7c57a-105">会議の形式が一対多のプレゼンテーションである。</span><span class="sxs-lookup"><span data-stu-id="7c57a-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="7c57a-106">1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。</span><span class="sxs-lookup"><span data-stu-id="7c57a-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="7c57a-107">PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。</span><span class="sxs-lookup"><span data-stu-id="7c57a-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="7c57a-108">音声が必要であり、ビデオも使用する場合がある。</span><span class="sxs-lookup"><span data-stu-id="7c57a-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="7c57a-109">通常、会議の開催者または開催者のアシスタントのいずれかが、会議を事前に設定している専用のユーザー。</span><span class="sxs-lookup"><span data-stu-id="7c57a-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="7c57a-110">(発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。</span><span class="sxs-lookup"><span data-stu-id="7c57a-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="7c57a-111">最大1000ユーザーの大規模な会議をサポートするには、共有ハードウェアモデルと非予約モデルの両方に関連する問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="7c57a-112">最大 1,000 ユーザーの会議に対応できる十分な CPU リソースとメモリ リソースを確保するには、ホスト側のフロントエンド サーバーで、他のインスタント メッセージング (IM) とプレゼンスやエンタープライズ VoIP のワークロードを一切ホストしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="7c57a-113">他の会議のサイズに関係なく、他の会議も主催する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7c57a-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="7c57a-114">つまり、最大1000ユーザーの会議を主催するには、1000ユーザーの大人数の会議を主催する専用の Lync Server プールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="7c57a-115">大規模な会議のホスティング専用の Lync Server プールは、1人のユーザーに対して同時に最大1000人の会議を開催する必要があります。そのため、フロントエンドの Serv から専用のサポートを受けるためには、帯域外のスケジュール処理を通じて事前に会議時間を予約する必要があります。サー.</span><span class="sxs-lookup"><span data-stu-id="7c57a-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="7c57a-116">一度に複数の大きな会議をサポートするには、複数の専用の大規模な会議プールを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c57a-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="7c57a-117">専用ユーザーが大規模な会議のオンラインの一部を実行して監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c57a-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="7c57a-118">この人は、組織の設定に応じて、開催者、開催者の代理人、または専用の大型会議のサポートチームのメンバーである場合があります。</span><span class="sxs-lookup"><span data-stu-id="7c57a-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="7c57a-119">以下のセクションでは、大規模な会議用の専用プールを実装する方法について説明します。これには、大規模な会議のシナリオをサポートするために Lync Server 2013 を使用するためのベストプラクティスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c57a-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7c57a-120">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7c57a-120">In This Section</span></span>

  - [<span data-ttu-id="7c57a-121">Lync Server 2013 での大規模な会議のサポートの設定</span><span class="sxs-lookup"><span data-stu-id="7c57a-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="7c57a-122">Lync Server 2013 での大規模な会議の管理</span><span class="sxs-lookup"><span data-stu-id="7c57a-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


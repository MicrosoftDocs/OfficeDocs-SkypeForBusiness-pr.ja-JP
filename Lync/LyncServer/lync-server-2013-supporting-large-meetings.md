---
title: 'Lync Server 2013: 大規模会議のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73c9a5d2ad4688f622298378c84b61574048a3b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="4e084-102">Lync Server 2013 を使用した大規模会議のサポート</span><span class="sxs-lookup"><span data-stu-id="4e084-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e084-103">_**トピックの最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4e084-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4e084-104">大規模な会議には次の特性があるため、前のセクションで説明したテスト モデルは採用されません。</span><span class="sxs-lookup"><span data-stu-id="4e084-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="4e084-105">会議の形式が一対多のプレゼンテーションである。</span><span class="sxs-lookup"><span data-stu-id="4e084-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="4e084-106">1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。</span><span class="sxs-lookup"><span data-stu-id="4e084-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="4e084-107">PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。</span><span class="sxs-lookup"><span data-stu-id="4e084-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="4e084-108">音声が必要であり、ビデオも使用する場合がある。</span><span class="sxs-lookup"><span data-stu-id="4e084-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="4e084-109">専任担当者 (通常は会議の開催者または開催者の補佐役) がかなり前から会議を設定する。</span><span class="sxs-lookup"><span data-stu-id="4e084-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="4e084-110">(発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。</span><span class="sxs-lookup"><span data-stu-id="4e084-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="4e084-111">最大 1,000 ユーザーの大規模な会議をサポートするには、共有ハードウェア モデルと予約なしモデルの両方に関する問題に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e084-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="4e084-112">最大1000ユーザーの会議に十分な CPU およびメモリリソースを確保するには、ホストするフロントエンドサーバーが他のインスタントメッセージング (IM) とプレゼンスまたはエンタープライズ Voip ワークロードをホストしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e084-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="4e084-113">また、会議の規模に関係なく、他の会議をホストしないようにすることも必要です。</span><span class="sxs-lookup"><span data-stu-id="4e084-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="4e084-114">これは、最大1000ユーザーの会議をホストするために、最大で1000ユーザーの大規模な会議をホストする専用の Lync Server プールを個別に設定する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4e084-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="4e084-115">大規模な会議をホストするための専用の Lync Server プールでは、1つの会議を同時に最大1000のユーザーに対して1つだけホストする必要があるため、フロントエンド Serv からの専用サポートを確保するために、会議の時間を事前に帯域外のスケジューリングプロセスを介して予約する必要があります。ばり.</span><span class="sxs-lookup"><span data-stu-id="4e084-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="4e084-116">一度に複数の大規模な会議をサポートする場合は、専用の大規模会議プールを複数設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e084-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="4e084-p103">大規模な会議のオンライン部分は専任担当者が実行し、監視することをお勧めします。この担当者は、組織の設定に応じて、開催者、開催者または発表者の代理人、大規模な会議の専任サポート チームのメンバーのいずれでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="4e084-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="4e084-119">次のセクションでは、大規模な会議のための専用プールを実装する方法について説明します。これには、Lync Server 2013 を使用して大規模な会議のシナリオをサポートするためのベストプラクティスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e084-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e084-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4e084-120">In This Section</span></span>

  - [<span data-ttu-id="4e084-121">Lync Server 2013 での大規模会議のサポートの設定</span><span class="sxs-lookup"><span data-stu-id="4e084-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="4e084-122">Lync Server 2013 での大規模な会議の管理</span><span class="sxs-lookup"><span data-stu-id="4e084-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


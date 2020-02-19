---
title: 'Lync Server 2013: ユーザーモデル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca76a6b6bbe8f2cf028f063c9c1bd9d37b35b5bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="dc0f1-102">Lync Server 2013 のユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc0f1-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="dc0f1-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="dc0f1-104">ここで説明するユーザーモデルは、「capacity [planning For Lync Server 2013 in user モデル](lync-server-2013-capacity-planning-using-the-user-models.md)」で説明されている容量計画の測定値および推奨事項の基礎を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="dc0f1-105">Lync Server 2013 のユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="dc0f1-106">次の表では、Lync Server 2013 の登録、連絡先、インスタントメッセージング (IM)、プレゼンスのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="dc0f1-107">環境および登録のユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-108">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-108">Category</span></span></th>
<th><span data-ttu-id="dc0f1-109">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-110">展開の規模と分散</span><span class="sxs-lookup"><span data-stu-id="dc0f1-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-111">3 つの中央サイトがあり、サイトごとにフロントエンド プールが 1 つある大規模な展開をモデル化します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-112">Active Directory ユーザーの割合</span><span class="sxs-lookup"><span data-stu-id="dc0f1-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-113">組織内のすべての Active Directory ユーザーの70% が Lync Server に対して有効になっていると想定しています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="dc0f1-114">有効になっているユーザーの80% は毎日 Lync Server にログオンしています (80% 同時実行)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="dc0f1-115">この同時ユーザー数は、以降の説明における数値の基盤です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-116">Active Directory の変更</span><span class="sxs-lookup"><span data-stu-id="dc0f1-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-117">ユーザー総数の0.5% は毎週 Active Directory 内の Lync に対して作成され、有効になっていると想定しています。また、ユーザーの合計数の0.5% は、Active Directory と Lync から毎週使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="dc0f1-118">ユーザーの5% は、少なくとも1つの Active Directory 属性が毎週変更されています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-119">Active Directory 配布グループ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p103">ここでは、組織の Active Directory 配布グループの数を Active Directory のすべてのユーザーの数の 3 倍に想定しています。配布グループのサイズは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-122">64% が 2 ～ 30 ユーザー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-123">13% が 31 ～ 50 ユーザー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-124">10% が 51 ～ 100 ユーザー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-125">13% が 101 ～ 500 ユーザー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-126">VoIP (ボイス オーバー IP) ユーザー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-127">Lync Server ユーザーの60% は統合コミュニケーション (UC) に対して有効になっています (つまり、自分の電話番号は Lync Server によって所有されています)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-128">登録済みクライアントの配分</span><span class="sxs-lookup"><span data-stu-id="dc0f1-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-129">クライアントの65% は lync および Lync Phone Edition を含む Lync 2013 ソフトウェアを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="dc0f1-130">以前のバージョンの Lync からクライアントソフトウェアを実行しているクライアントの30%</span><span class="sxs-lookup"><span data-stu-id="dc0f1-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="dc0f1-131">Lync Web App を使用しているクライアントの5%</span><span class="sxs-lookup"><span data-stu-id="dc0f1-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="dc0f1-132">モビリティが有効になっている場合、ユーザーの40% が以前に説明した他の登録済みクライアントオプションと同時にモビリティを使用していると仮定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="dc0f1-133">この例では、クライアントの複数のプレゼンス (MPOP) の比率は 1: 1.9 です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="dc0f1-134">モビリティを無効にすると、MPOP 比率は 1:1.5 になります。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-135">リモート ユーザーの分散</span><span class="sxs-lookup"><span data-stu-id="dc0f1-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-136">70% のユーザーが内部接続する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="dc0f1-137">ユーザーの 30% はエッジ サーバーおよびディレクターを介して接続する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-138">連絡先の分散</span><span class="sxs-lookup"><span data-stu-id="dc0f1-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p105">ユーザーは最大で 1,000 件の連絡先を登録できます。1,000 件の連絡先があるユーザーは全体の 1% 未満です。ユーザーの 25% 未満が 100 件以上の連絡先を登録する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="dc0f1-p106">平均 80 件のユーザーの連絡先がパブリック クラウド接続を利用します。それらのユーザーの内訳けは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-p107">連絡先の 50% は組織内に存在する。それらのユーザーの 10% はリモート ユーザーで、ファイアウォールの外側から接続する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-146">連絡先の 40% はパブリック クラウド ユーザー (AOL、Yahoo!、MSN、Google Talk など)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-147">連絡先の 10% がフェデレーション パートナー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="dc0f1-148">2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="dc0f1-149">アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="dc0f1-150">メッセンジャーサービスが終了するまでの期間。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="dc0f1-151">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="dc0f1-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="dc0f1-152">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-152">has been announced.</span></span> <span data-ttu-id="dc0f1-153">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc0f1-154">PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="dc0f1-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="dc0f1-155">Messenger.</span></span> <span data-ttu-id="dc0f1-156">このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="dc0f1-157">Lync は、組織間や世界中の個人と接続するための強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="dc0f1-158">Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="dc0f1-159">Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="dc0f1-p111">平均で 50 件のユーザーの連絡先ではパブリック クラウド接続を利用できません。それらのユーザーの内訳けは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-p112">連絡先の 80% は組織内に存在する。それらのユーザーの 10% はリモート ユーザーで、ファイアウォールの外側から接続する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-164">連絡先の 20% がフェデレーション パートナー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="dc0f1-p113">各ユーザーの連絡先リストに 1 つの配布グループが含まれる。パフォーマンス テスト用に、配布グループは常に拡大していると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="dc0f1-167">ユーザーの連絡先の 25% で XMPP が使用される。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-168">セッション時間</span><span class="sxs-lookup"><span data-stu-id="dc0f1-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p114">ユーザー ログオン セッションの平均存続時間は 12 時間。すべてのユーザーがセッションの開始から 120 分以内にログオンする。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="dc0f1-171">IM とプレゼンスのユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-172">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-172">Category</span></span></th>
<th><span data-ttu-id="dc0f1-173">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-174">ピアツーピア IM セッション</span><span class="sxs-lookup"><span data-stu-id="dc0f1-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-175">各ユーザーの 1 日あたりのピアツーピア IM セッション数の平均は 6。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="dc0f1-176">セッションあたりのインスタント メッセージ数は 10。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="dc0f1-177">各メッセージは2つの SIP INFO メッセージと2つの SIP 200 OK メッセージによって照合され&lt;ます&gt; ("Name が入力しています" などのステータスインジケーター用)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-178">プレゼンス ポーリング</span><span class="sxs-lookup"><span data-stu-id="dc0f1-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p115">全体では、プレゼンス ポーリングの平均数を 1 時間ごとに 1 ユーザーあたり 60 回と想定します。また、ユーザーごとに次の平均を想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-p116">ユーザーの組織タブ (連絡先リストではない) でのユーザーのプレゼンスのポーリング回数は 1 日 1 回。ユーザーの組織タブでの連絡先なしの平均数は 15 ユーザー。連絡先カードの表示操作回数は 1 日 2 回。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-184">1 時間あたり 1 回と推定して、ユーザーが別のユーザーをクリックして会話を始めるごとに 1 回のプレゼンス ポーリング。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-p117">1 時間あたりのユーザー検索数は 6 回。検索を実行するたびに、検索結果一覧のすべてのユーザーに対してバッチ ポーリングが送信されます。検索結果の平均サイズは 20 と想定します。検索結果が画面に表示されたままの場合、バッチ ポーリングは 5 分ごとに更新されます。このような更新が 1 時間ごとに 2 回行われると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-189">ユーザーが Outlook で電子メールを開くかプレビューするときに、電子メールの [宛先] および [CC] フィールドで行われるユーザーのプレゼンスのポーリングでは、1 時間あたりの電子メールを 5 通、電子メールあたりのユーザー数を 4 人と推定しました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-190">プレゼンス サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="dc0f1-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p118">ユーザーが別のユーザーを連絡先として追加するとき、最初のユーザーは 2 番目のユーザーに関する 5 つのカテゴリの情報にサブスクライブ<em></em>します。これらのカテゴリの更新情報は、最初のユーザーに自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="dc0f1-193">クライアントごとに 1 つのバッチ サブスクリプション要求が送信され、平均で 40 件の連絡先のプレゼンスが取得されます。さらに、フェデレーションの連絡先のプレゼンスを取得するために、追加の 40 件のダイアログが送信されます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="dc0f1-194">展開された配布グループのメンバーのプレゼンスは、ポーリングではなく永続的なプレゼンス サブスクリプションによって検索され、2 時間ごとにユーザーあたり 1 回の展開としてモデル化されます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="dc0f1-p119">ユーザーがログインすると<em>短期サブスクリプション</em>が発生し、そのユーザーのすべての連絡先についてバッチ サブスクリプションが実行され、その後すぐにユーザーはログオフします。1 時間ごとに 1 ユーザーあたり 6 回の短期サブスクリプションが発生し、個々のサブスクリプションは 10 分間継続すると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-197">プレゼンス公開</span><span class="sxs-lookup"><span data-stu-id="dc0f1-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-198">プレゼンス状態は平均で 1 時間ごとに 1 ユーザーあたり 4 回公開され、最大数は 1 時間ごとに 1 ユーザーあたり 6 回です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-199">プレゼンス ドキュメント サイズ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-200">完全なプレゼンス ドキュメントの平均サイズは 4K、最大で 25K と想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-201">次の表に、アドレス帳使用量のユーザー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="dc0f1-202">アドレス帳使用量のユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-203">アドレス帳検索モード</span><span class="sxs-lookup"><span data-stu-id="dc0f1-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="dc0f1-204">使用方法</span><span class="sxs-lookup"><span data-stu-id="dc0f1-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-205">アドレス帳 Web クエリのみ (すべてのクエリはアドレス帳 Web クエリ サービスで実行)</span><span class="sxs-lookup"><span data-stu-id="dc0f1-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-206">プレフィックス クエリは、1 日あたりユーザーごとに 4 回。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="dc0f1-p120">完全一致クエリは、1 日あたりユーザーごとに 60 回。それらの 40% はバッチ処理され、クエリあたりの平均連絡先は 20 件です。クエリの残りの 60% は、連絡先が 1 つの場合です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="dc0f1-p121">写真クエリは、1 日あたりユーザーごとに 25 回。24 回は 1 枚の写真の場合、もう 1 回は平均連絡先数が 20 件のバッチ クエリです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="dc0f1-212">組織全体の検索クエリは、1 日あたりユーザーごとに 1 回。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-p122">混合型モード、アドレス帳ファイル クエリと Web クエリの両方を使用する。既定のモード。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-215">写真クエリと全体的な組織検索クエリの 2 つのタイプのクエリだけをネットワークに向けて送信する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="dc0f1-p123">写真クエリは、1 日あたりユーザーごとに 25 回。24 回は 1 枚の写真の場合、もう 1 回は平均連絡先数が 20 件のバッチ クエリです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="dc0f1-218">組織全体の検索クエリは、1 日あたりユーザーごとに 1 回。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-219">次の表で電話会議モデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="dc0f1-220">電話会議モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-221">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-221">Category</span></span></th>
<th><span data-ttu-id="dc0f1-222">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-223">予約され&quot;た会議&quot;と Meet now ミーティング</span><span class="sxs-lookup"><span data-stu-id="dc0f1-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-224">60% が予約され、40% が予約なし。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="dc0f1-225">予定されたミーティングのうち、80% は割り当て済みの電話会議 (定期的な電話会議の各回)、10% は 1 回限りの公開されたミーティング、8% は 1 回限りの匿名のミーティング、2% は 1 回限りの非公開ミーティングと想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-226">電話会議クライアントの配分</span><span class="sxs-lookup"><span data-stu-id="dc0f1-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-227">予定されたミーティングの場合:</span><span class="sxs-lookup"><span data-stu-id="dc0f1-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-228">電話会議ユーザーの65% は Lync 2013 を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-229">電話会議ユーザーの5% が Microsoft Lync Web App を使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-230">電話会議ユーザーの30% は、Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007、Microsoft Office Communicator Web Access (2007 リリース) を含む以前のクライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="dc0f1-231">予約されていないミーティングの場合:</span><span class="sxs-lookup"><span data-stu-id="dc0f1-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc0f1-232">電話会議ユーザーの70% は Lync 2013 を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-233">電話会議ユーザーの30% は、Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007、Microsoft Office Communicator Web Access (2007 リリース) を含む以前のクライアントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-234">ミーティングの同時開催</span><span class="sxs-lookup"><span data-stu-id="dc0f1-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p124">ユーザーの 5% が勤務時間中に会議に出席。したがって、80,000 ユーザー プールでは、最大で 4,000 人のユーザーが任意の時刻に同時に会議に出席することが可能です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-237">ミーティング オーディオの配分</span><span class="sxs-lookup"><span data-stu-id="dc0f1-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-238">混合型 VoIP オーディオおよびダイヤルイン電話会議が 40%、ダイヤルイン ユーザーに対する VoIP ユーザーの比率は 3 : 1。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="dc0f1-239">VoIP オーディオのみが 35%。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="dc0f1-240">ダイヤルイン電話会議オーディオのみが 15%。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="dc0f1-241">オーディオなしが 10% (IM のみの電話会議、送信される平均メッセージ数がユーザーあたり 5 件)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-242">会議でのメディア混合</span><span class="sxs-lookup"><span data-stu-id="dc0f1-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-243">電話会議の 75% が Web 会議であり、オーディオと他のいくつかのコラボレーション モダリティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="dc0f1-244">これらの電話会議の場合、その他のコラボレーション方法は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="dc0f1-245">これらの数字は、1 つの電話会議で複数のコラボレーション方法を使用できるため、合計すると 100% 以上になります。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="dc0f1-p125">50% がアプリケーション共有を追加する。ピーク時には 1 人のユーザーが 1 秒あたり 1.1 MB のデータを送信する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-248">50% がインスタント メッセージングを追加する (ユーザーあたり平均 2 メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-p126">20% がデータ コラボレーション (PowerPoint、ホワイトボードなど) を追加する。このうち、PowerPoint ファイルの平均サイズを 10 MB (ビデオの埋め込みなしの場合) または 30 MB (ビデオの埋め込みありの場合) とし、提示される PowerPoint ファイルの平均数は電話会議あたり 2 個。ホワイトボードあたりの平均コメント数は 20。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-p127">20% がビデオを追加する。これらのユーザーのうち、70% はマルチビュー ビデオが有効な会議に参加し、各ユーザーが 2 ～ 3 個のビデオ ストリームを受け取る。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="dc0f1-253">15% が共有メモを追加する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-254">ミーティング参加者の分散</span><span class="sxs-lookup"><span data-stu-id="dc0f1-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-255">50% が内部の認証されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="dc0f1-256">25% がリモート アクセスの認証されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="dc0f1-257">15% が匿名ユーザー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="dc0f1-258">10% がフェデレーション ユーザー。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-259">ミーティング参加の配分</span><span class="sxs-lookup"><span data-stu-id="dc0f1-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-260">ユーザーは最初の 5 分以内にミーティングに参加するものとしてシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-261">通常のフロントエンドプールでは、Lync Server 2013 でサポートされている会議の最大サイズは250ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="dc0f1-262">各プールは、250 ユーザーのミーティングを一度に 1 つホストできます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="dc0f1-263">この大規模なミーティングが行われている間に、プールでは別の小規模な電話会議もホストできます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="dc0f1-264">さらに、ミーティングをホストするための専用プールをセットアップすることで、最大 1000 ユーザーのミーティングをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="dc0f1-265">詳細については、「 [Lync Server 2013 での大規模会議のサポート](lync-server-2013-support-for-large-meetings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="dc0f1-266">電話会議は次のようにシミュレートされました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="dc0f1-267">電話会議の 85% は参加者が 4 人。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="dc0f1-268">電話会議の 10% は参加者が 6 人。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="dc0f1-269">電話会議の 5% は参加者が 11 人。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="dc0f1-270">250 ユーザーの大規模な電話会議が 1 回。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-270">One large conference of 250 users.</span></span>

<span data-ttu-id="dc0f1-271">次の表に、ダイヤルイン ユーザーが関係する電話会議のユーザー モデルについての詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="dc0f1-272">ダイヤルイン会議のユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-273">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-273">Category</span></span></th>
<th><span data-ttu-id="dc0f1-274">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-275">認証/匿名</span><span class="sxs-lookup"><span data-stu-id="dc0f1-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p129">発信者の 70% は匿名で参加し、記録された名前の入力を求められる。30% は認証されたユーザーとして参加する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-278">通話時間と保留音</span><span class="sxs-lookup"><span data-stu-id="dc0f1-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-279">保留音なしでの平均通話時間: 50 秒です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="dc0f1-280">コールイン ユーザーの 50% が平均で 5 分間保留音を聞く。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-281">デュアルトーン多重周波数 (DTMF)</span><span class="sxs-lookup"><span data-stu-id="dc0f1-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p130">ダイヤルインのみの電話会議の 15% に電話会議の主催者がいる。ダイヤルイン ユーザーを含む混合型電話会議の 10% にも電話会議の主催者がいる。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="dc0f1-284">電話会議の主催者の 20% が電話会議あたり 2 つの DTMF コマンドを使用する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-285">アナウンスの言語</span><span class="sxs-lookup"><span data-stu-id="dc0f1-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-286">シミュレーションでは、アナウンスの言語として英語を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-287">次の表に、電話会議ロビーのユーザー モデルについての詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="dc0f1-288">電話会議ロビーのユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-289">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-289">Category</span></span></th>
<th><span data-ttu-id="dc0f1-290">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-291">ロビー内のユーザー数</span><span class="sxs-lookup"><span data-stu-id="dc0f1-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-292">ダイヤルイン ユーザーの 5% がロビーを通過し、他のユーザーの 25% がロビーを通過する</span><span class="sxs-lookup"><span data-stu-id="dc0f1-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-293">ロビーからの承認</span><span class="sxs-lookup"><span data-stu-id="dc0f1-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-294">シミュレーションでは、すべてのユーザーがクライアントのタイムアウト前に発表者によって承認されました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-295">次の表に、他のピアツーピア セッションのユーザー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="dc0f1-296">ピアツーピア セッションのユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-297">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-297">Category</span></span></th>
<th><span data-ttu-id="dc0f1-298">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-299">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="dc0f1-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-300">各ユーザーが 1 か月あたり 5 つのピアツーピア アプリケーション共有セッション (1 日あたりの平均は 0.25 セッション) に参加する。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-301">ファイル送信</span><span class="sxs-lookup"><span data-stu-id="dc0f1-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-p131">各ユーザーが (IM セッションの一部として) 1 月あたり 1 つのピアツーピア ファイル転送セッション (1 日あたりの平均は 0.05 セッション) に参加する。転送される平均的なセッション ファイル サイズは 1 MB です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc0f1-304">次の表に、 ポリシーのユーザー モデルを示します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="dc0f1-305">ポリシー ユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="dc0f1-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc0f1-306">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="dc0f1-306">Category</span></span></th>
<th><span data-ttu-id="dc0f1-307">説明</span><span class="sxs-lookup"><span data-stu-id="dc0f1-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc0f1-308">電話会議、プレゼンス、およびアーカイブのポリシー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-309">1 個のグローバル ポリシー、10 個のタグ電話会議ポリシー、4 個のアーカイブ ポリシー、および 10 個のタグ プレゼンス ポリシーがあると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc0f1-310">音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="dc0f1-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="dc0f1-311">サイトごとに 1 個のグローバル ポリシーと 2 個のタグ ポリシーがあると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="dc0f1-312">サイトの 100% にサイト ポリシーがあり、ユーザーの 30% にユーザー単位のポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="dc0f1-313">サイトごとに 1 個のダイヤル プランおよび 2 個のルートがあると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="dc0f1-314">最繁時</span><span class="sxs-lookup"><span data-stu-id="dc0f1-314">Busy Hour</span></span>

<span data-ttu-id="dc0f1-p133">ピアツーピア セッションの場合、ピーク負荷は最繁時呼数 (BHCA) を使用して計算します。この音声業界用語では、1 日のすべての通話の 50% が 20% の時間で完了すると想定しています。以下の式を使用して計算します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="dc0f1-318">パフォーマンス テストでは、最低でも 1 日あたり 1.6 時間、VoIP セッションと他のピアツーピア セッションを最繁時負荷で実行することによって、最繁時のシミュレーションを行いました。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="dc0f1-p134">電話会議のピーク負荷では、1 日 (8 時間) のすべての電話会議の 75% がピーク時の 4 時間で行われると想定しています。それらのピーク時の負荷は、平均電話会議負荷の 1.5 倍です。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="dc0f1-321">エンタープライズ Voip から PSTN への通話</span><span class="sxs-lookup"><span data-stu-id="dc0f1-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="dc0f1-322">エンタープライズ Voip 通話には、次の前提が適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="dc0f1-323">ユーザーの50% はエンタープライズ Voip に対応しており、これらのユーザーの60% は PSTN 通話が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="dc0f1-p135">PSTN 通話が有効になっているユーザーはそれぞれ、混雑時に 4 回の PSTN 通話を行う。各通話の通話時間は 3 分。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="dc0f1-326">これらの PSTN 音声通話の 65% でメディア バイパスが使用される。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="dc0f1-327">身体</span><span class="sxs-lookup"><span data-stu-id="dc0f1-327">Mobility</span></span>

<span data-ttu-id="dc0f1-p136">登録ユーザーの 40% はモビリティが有効になっていると想定します。モビリティが有効になっている各ユーザーについて、そのユーザーのその他の MPOP インスタンスのアクティビティに加えてモバイル クライアントのアクティビティが行われます。ただし、電話会議でのやり取りは例外であり、その場合はモビリティ クライアントは電話会議への参加に使用できるクライアントの種類の 1 つに過ぎません。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="dc0f1-330">常設チャット</span><span class="sxs-lookup"><span data-stu-id="dc0f1-330">Persistent Chat</span></span>

<span data-ttu-id="dc0f1-331">登録ユーザーの 25% は常設チャット セッションに参加し、次のような特性を持つと想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="dc0f1-332">ユーザーあたり平均 1.5 のチャット ルーム</span><span class="sxs-lookup"><span data-stu-id="dc0f1-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="dc0f1-333">各チャット ルームでは 1 時間ごとに 12 回のポーリング要求が行われ、それぞれ平均で 10 ユーザーを対象とする</span><span class="sxs-lookup"><span data-stu-id="dc0f1-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="dc0f1-334">応答グループとコール パーク</span><span class="sxs-lookup"><span data-stu-id="dc0f1-334">Response Group and Call Park</span></span>

<span data-ttu-id="dc0f1-p137">登録ユーザーの 0.15% が応答グループに属していると想定します。また、登録ユーザーの 0.02% が任意の時点でコール パークを使用すると想定します。</span><span class="sxs-lookup"><span data-stu-id="dc0f1-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


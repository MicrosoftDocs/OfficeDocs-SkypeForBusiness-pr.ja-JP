---
title: SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="56d3c-102">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="56d3c-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56d3c-103">_**最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="56d3c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="56d3c-104">フェデレーション、パブリックインスタントメッセージング接続、および拡張メッセージングとプレゼンスプロトコル (XMPP) では、フェデレーションユーザーのさまざまなクラスの外部ユーザーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="56d3c-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="56d3c-105">フェデレーションされた Lync Server 展開または XMPP の展開のユーザーは、限定されたサービスのセットにアクセスし、外部展開によって認証されます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="56d3c-106">リモートユーザーは、Lync Server 展開のメンバーであり、展開によって提供されるすべてのサービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="56d3c-107">AOL および Yahoo! の2014年6月の終了日</span><span class="sxs-lookup"><span data-stu-id="56d3c-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="56d3c-108">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="56d3c-108">has been announced.</span></span> <span data-ttu-id="56d3c-109">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56d3c-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="56d3c-110">パブリックインスタントメッセージング接続は、lync Server クライアントが Lync 2013 を使って、構成済みのパブリックインスタントメッセージングパートナーにアクセスできるようにする特別な種類のフェデレーションです。</span><span class="sxs-lookup"><span data-stu-id="56d3c-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="56d3c-111">現在のパブリックインスタントメッセージング接続パートナーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56d3c-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="56d3c-112">America Online</span><span class="sxs-lookup"><span data-stu-id="56d3c-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="56d3c-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="56d3c-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="56d3c-114">!\!</span><span class="sxs-lookup"><span data-stu-id="56d3c-114">Yahoo\!</span></span>

<span data-ttu-id="56d3c-115">パブリックインスタントメッセージングの接続構成を使うと、Lync ユーザーは次の方法でパブリックインスタントメッセージング (im) 接続にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="56d3c-116">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="56d3c-116">IM and Presence</span></span>

  - <span data-ttu-id="56d3c-117">Lync クライアントでのパブリックインスタントメッセージング接続の連絡先の表示</span><span class="sxs-lookup"><span data-stu-id="56d3c-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="56d3c-118">連絡先との IM 会話をする人</span><span class="sxs-lookup"><span data-stu-id="56d3c-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="56d3c-119">Windows Live ユーザとの音声通話とビデオ通話</span><span class="sxs-lookup"><span data-stu-id="56d3c-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="56d3c-120">Lync server federation は、Lync Server の展開とその他の Office Communications Server 2007 R2 または Lync Server の展開との間の契約を定義します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="56d3c-121">Lync Server のフェデレーション構成により、Lync ユーザーは次の方法でフェデレーションユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="56d3c-122">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="56d3c-122">IM and Presence</span></span>

  - <span data-ttu-id="56d3c-123">Lync クライアントでのフェデレーションされた連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="56d3c-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="56d3c-124">XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコルに基づいて外部展開を定義します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="56d3c-125">XMPP の構成により、Lync ユーザーは次の方法で許可された XMPP ドメインユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="56d3c-126">IM とプレゼンス–人物との連絡のみ</span><span class="sxs-lookup"><span data-stu-id="56d3c-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="56d3c-127">Lync クライアントでの XMPP フェデレーション連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="56d3c-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="56d3c-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="56d3c-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="56d3c-130">エッジサーバーの外部フェデレーション、パブリックインスタントメッセージング接続、および XMPP ユーザー展開プロセス</span><span class="sxs-lookup"><span data-stu-id="56d3c-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56d3c-131">段階</span><span class="sxs-lookup"><span data-stu-id="56d3c-131">Phase</span></span></th>
<th><span data-ttu-id="56d3c-132">ステップ</span><span class="sxs-lookup"><span data-stu-id="56d3c-132">Steps</span></span></th>
<th><span data-ttu-id="56d3c-133">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="56d3c-133">Permissions</span></span></th>
<th><span data-ttu-id="56d3c-134">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="56d3c-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56d3c-135">既存のエッジ展開に追加するオプションを決定する</span><span class="sxs-lookup"><span data-stu-id="56d3c-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="56d3c-136">トポロジビルダーを実行して、エッジサーバーの設定を編集し、トポロジを作成して公開します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="56d3c-137">既存のエッジトポロジによって、中央管理ストアからエッジサーバーに変更がレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="56d3c-138">Domain Admins グループと RTCUniversalServerAdmins グループ</span><span class="sxs-lookup"><span data-stu-id="56d3c-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="56d3c-139">[ローカルユーザー] グループのメンバーであるアカウントを使用してトポロジを編集することはできますが、トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであるアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="56d3c-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="56d3c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d3c-141">セットアップの準備をする</span><span class="sxs-lookup"><span data-stu-id="56d3c-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="56d3c-142">システムの前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="56d3c-143">内部と外部の DNS レコードを構成し、パブリックインスタントメッセージング接続、Lync フェデレーション、および XMPP フェデレーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="56d3c-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="56d3c-144">展開しているフェデレーションの種類をサポートするために、ファイアウォールでポートおよびプロトコルを構成する</span><span class="sxs-lookup"><span data-stu-id="56d3c-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="56d3c-145">公開証明書を取得してインストールします。</span><span class="sxs-lookup"><span data-stu-id="56d3c-145">Obtain and install public certificates.</span></span> <span data-ttu-id="56d3c-146">証明書を取得するために必要な時間は、証明書が発行される証明機関 (CA) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="56d3c-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="56d3c-147">この手順は、展開のこの時点では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="56d3c-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="56d3c-148">この手順をこの時点で実行しない場合は、エッジサーバーの構成中に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56d3c-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="56d3c-149">エッジサーバーサービスは、証明書が取得されるまで開始できません。</span><span class="sxs-lookup"><span data-stu-id="56d3c-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="56d3c-150">組織に応じて、通常、これらの役割は多数のワークグループに分割されます。</span><span class="sxs-lookup"><span data-stu-id="56d3c-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="56d3c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d3c-152">フェデレーションシナリオ用にエッジサーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="56d3c-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="56d3c-153">エクスポートされたトポロジ構成ファイルを各エッジサーバーにトランスポートするか、複製を完了できるようにする</span><span class="sxs-lookup"><span data-stu-id="56d3c-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="56d3c-154">展開ウィザードを再実行して、フェデレーション用のサポートコンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="56d3c-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="56d3c-155">エッジサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="56d3c-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="56d3c-156">エッジサーバーごとに証明書を要求およびインストールする</span><span class="sxs-lookup"><span data-stu-id="56d3c-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="56d3c-157">Edge Server サービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="56d3c-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="56d3c-158">管理者グループ</span><span class="sxs-lookup"><span data-stu-id="56d3c-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="56d3c-159"><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013 での Lync フェデレーションのセットアップ</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="56d3c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセージング接続の設定</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="56d3c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013 XMPP フェデレーションのセットアップ</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56d3c-162">外部ユーザーアクセスのサポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="56d3c-163">Lync Server コントロールパネルの外部ユーザーアクセスを使用する</span><span class="sxs-lookup"><span data-stu-id="56d3c-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="56d3c-164">フェデレーションされたユーザーまたはパブリックユーザーとの通信を有効にするための外部アクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="56d3c-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="56d3c-165">SIP フェデレーションドメインを構成してドメインを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="56d3c-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="56d3c-166">パブリックインスタントメッセージング接続プロバイダーの SIP フェデレーションプロバイダーを有効にする</span><span class="sxs-lookup"><span data-stu-id="56d3c-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="56d3c-167">Xmpp ドメインごとに XMPP フェデレーションパートナーを構成する</span><span class="sxs-lookup"><span data-stu-id="56d3c-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="56d3c-168">CSAdministrator ロールに割り当てられている RTCUniversalServerAdmins グループまたはユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="56d3c-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="56d3c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="56d3c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56d3c-171">エッジサーバーの構成を確認する</span><span class="sxs-lookup"><span data-stu-id="56d3c-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="56d3c-172">内部サーバーからのサーバー接続と構成データのレプリケーションを確認する</span><span class="sxs-lookup"><span data-stu-id="56d3c-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="56d3c-173">ユーザー接続の確認のために CSAdministrator ロールに割り当てられている複製、RTCUniversalServerAdmins グループ、またはユーザーアカウントを確認するには、フェデレーションユーザーの種類ごとにユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="56d3c-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="56d3c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジの展開の検証</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="56d3c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション</a></span><span class="sxs-lookup"><span data-stu-id="56d3c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


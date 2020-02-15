---
title: SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d97966d0a5062b133e9802f97ff77934ba29300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="f4071-102">Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成</span><span class="sxs-lookup"><span data-stu-id="f4071-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4071-103">_**トピックの最終更新日:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f4071-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f4071-104">フェデレーション、パブリック インスタント メッセージング接続、および XMPP (Extensible Messaging and Presence Protocol) は、別の外部ユーザー クラス、すなわちフェデレーション ユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f4071-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="f4071-105">フェデレーション Lync Server 展開または XMPP 展開のユーザーは、限定されたサービスのセットにアクセスでき、外部展開によって認証されます。</span><span class="sxs-lookup"><span data-stu-id="f4071-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="f4071-106">リモートユーザーは、Lync Server 展開のメンバーであり、展開によって提供されるすべてのサービスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4071-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f4071-107">AOL および Yahoo! の2014年6月の寿命の終了日</span><span class="sxs-lookup"><span data-stu-id="f4071-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f4071-108">が発表されました。</span><span class="sxs-lookup"><span data-stu-id="f4071-108">has been announced.</span></span> <span data-ttu-id="f4071-109">詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4071-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="f4071-110">パブリックインスタントメッセージング接続は、lync Server クライアントが Lync 2013 を使用して構成済みのパブリックインスタントメッセージングパートナーにアクセスできるようにする特別な種類のフェデレーションです。</span><span class="sxs-lookup"><span data-stu-id="f4071-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="f4071-111">現時点のパブリック インスタント メッセージング接続パートナーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4071-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="f4071-112">America Online</span><span class="sxs-lookup"><span data-stu-id="f4071-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="f4071-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="f4071-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="f4071-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="f4071-114">Yahoo\!</span></span>

<span data-ttu-id="f4071-115">パブリック インスタント メッセージング接続を構成すると、Lync ユーザーは次の方法でパブリック インスタント メッセージング接続ユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4071-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="f4071-116">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="f4071-116">IM and Presence</span></span>

  - <span data-ttu-id="f4071-117">パブリック インスタント メッセージング接続の連絡先を Lync クライアント内に表示</span><span class="sxs-lookup"><span data-stu-id="f4071-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="f4071-118">連絡先との 1 対 1 の IM 会話</span><span class="sxs-lookup"><span data-stu-id="f4071-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="f4071-119">Windows Live ユーザーとの音声およびビデオ通話</span><span class="sxs-lookup"><span data-stu-id="f4071-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="f4071-p104">Lync Server フェデレーションは、Lync Server の展開と他の Office Communications Server 2007 R2 または Lync Server の展開との間の合意を定義します。Lync Server フェデレーションを構成すると、Lync ユーザーは次の方法でフェデレーション ユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4071-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="f4071-122">IM とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="f4071-122">IM and Presence</span></span>

  - <span data-ttu-id="f4071-123">フェデレーションの連絡先を Lync クライアントに作成</span><span class="sxs-lookup"><span data-stu-id="f4071-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="f4071-p105">XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づく外部展開を定義します。XMPP を構成すると、Lync ユーザーは許可された XMPP ドメイン ユーザーに次の方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4071-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="f4071-126">IM およびプレゼンス (1 対 1 のみ)</span><span class="sxs-lookup"><span data-stu-id="f4071-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="f4071-127">XMPP フェデレーションからの連絡先を Lync クライアントに作成</span><span class="sxs-lookup"><span data-stu-id="f4071-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f4071-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="f4071-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="f4071-130">エッジ サーバー外部フェデレーション、パブリック インスタント メッセージング接続、および XMPP ユーザーの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="f4071-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4071-131">フェーズ</span><span class="sxs-lookup"><span data-stu-id="f4071-131">Phase</span></span></th>
<th><span data-ttu-id="f4071-132">手順</span><span class="sxs-lookup"><span data-stu-id="f4071-132">Steps</span></span></th>
<th><span data-ttu-id="f4071-133">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4071-133">Permissions</span></span></th>
<th><span data-ttu-id="f4071-134">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="f4071-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4071-135">既存のエッジ展開に追加するオプションを決める</span><span class="sxs-lookup"><span data-stu-id="f4071-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="f4071-136">トポロジビルダーを実行して、エッジサーバーの設定を編集し、トポロジを作成および公開します。</span><span class="sxs-lookup"><span data-stu-id="f4071-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="f4071-137">既存のエッジトポロジによって、中央管理ストアからエッジサーバーへの変更がレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="f4071-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="f4071-138">Domain Admins グループおよび RTCUniversalServerAdmins グループ。</span><span class="sxs-lookup"><span data-stu-id="f4071-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="f4071-139">ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを編集できますが、トポロジを公開するには Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであるアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="f4071-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="f4071-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</a></span><span class="sxs-lookup"><span data-stu-id="f4071-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4071-141">セットアップの準備をする</span><span class="sxs-lookup"><span data-stu-id="f4071-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f4071-142">システムの前提条件が適合していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4071-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="f4071-143">内部および外部 DNS レコードを構成して、パブリック インスタント メッセージング接続、Lync フェデレーション、および XMPP フェデレーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f4071-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="f4071-144">ファイアウォールのポートとプロトコルを構成して、展開するフェデレーションの種類をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f4071-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="f4071-p108">パブリック証明書を取得してインストールします。証明書の取得に必要な時間は、どの証明機関 (CA) が証明書を発行するかによって異なります。この時点で、この手順を必ずしも実行する必要はありません。この手順を実行しない場合は、エッジ サーバーの構成時に実行する必要があります。 証明書を取得しないと、エッジ サーバー サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="f4071-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f4071-150">組織に応じる (一般に、これらの役割は多数のワーク グループと切り離されるため)</span><span class="sxs-lookup"><span data-stu-id="f4071-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="f4071-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</a></span><span class="sxs-lookup"><span data-stu-id="f4071-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4071-152">フェデレーション シナリオ用にエッジ サーバーを設定する</span><span class="sxs-lookup"><span data-stu-id="f4071-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f4071-153">エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートするか、レプリケーションを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f4071-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="f4071-154">展開ウィザードを再実行して、フェデレーション用にサポートされているコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4071-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="f4071-155">エッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f4071-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="f4071-156">各エッジ サーバー用の証明書を要求してインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4071-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="f4071-157">エッジ サーバー サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f4071-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f4071-158">Administrators グループ。</span><span class="sxs-lookup"><span data-stu-id="f4071-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="f4071-159"><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013 での Lync フェデレーションのセットアップ</a></span><span class="sxs-lookup"><span data-stu-id="f4071-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f4071-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の設定</a></span><span class="sxs-lookup"><span data-stu-id="f4071-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f4071-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013 での XMPP フェデレーションのセットアップ</a></span><span class="sxs-lookup"><span data-stu-id="f4071-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4071-162">外部ユーザー アクセスのサポートの構成</span><span class="sxs-lookup"><span data-stu-id="f4071-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f4071-163">Lync Server コントロールパネルの外部ユーザーアクセスを使用する</span><span class="sxs-lookup"><span data-stu-id="f4071-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="f4071-164">外部アクセス ポリシーを構成して、フェデレーション ユーザーやパブリック ユーザーとの通信を有効します。</span><span class="sxs-lookup"><span data-stu-id="f4071-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="f4071-165">SIP フェデレーション ドメインを構成して、ドメインを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="f4071-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="f4071-166">パブリック インスタント メッセージング接続プロバイダーに対して SIP フェデレーション プロバイダーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f4071-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="f4071-167">XMPP ドメインごとに XMPP フェデレーション パートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="f4071-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f4071-168">RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="f4071-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="f4071-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスのサポートの構成</a></span><span class="sxs-lookup"><span data-stu-id="f4071-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f4071-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013 のパブリックプロバイダーに対するメディアの暗号化の構成</a></span><span class="sxs-lookup"><span data-stu-id="f4071-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4071-171">エッジ サーバー構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="f4071-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="f4071-172">内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4071-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="f4071-173">レプリケーションの確認には、RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウントが必要。ユーザー接続の確認には、フェデレーション ユーザーの種類ごとにユーザーが必要。</span><span class="sxs-lookup"><span data-stu-id="f4071-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="f4071-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジ展開の確認</a></span><span class="sxs-lookup"><span data-stu-id="f4071-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f4071-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</a></span><span class="sxs-lookup"><span data-stu-id="f4071-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


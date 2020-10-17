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
ms.openlocfilehash: 7f3fa4f3b78f53df101da42a2e6b7630cdfb71dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537074"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリックインスタントメッセージングの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

フェデレーション、パブリック インスタント メッセージング接続、および XMPP (Extensible Messaging and Presence Protocol) は、別の外部ユーザー クラス、すなわちフェデレーション ユーザーを定義します。 フェデレーション Lync Server 展開または XMPP 展開のユーザーは、限定されたサービスのセットにアクセスでき、外部展開によって認証されます。 リモートユーザーは、Lync Server 展開のメンバーであり、展開によって提供されるすべてのサービスにアクセスできます。

<div>


> [!NOTE]
> AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。



</div>

パブリックインスタントメッセージング接続は、lync Server クライアントが Lync 2013 を使用して構成済みのパブリックインスタントメッセージングパートナーにアクセスできるようにする特別な種類のフェデレーションです。 現時点のパブリック インスタント メッセージング接続パートナーは次のとおりです。

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    Yahoo\!

パブリック インスタント メッセージング接続を構成すると、Lync ユーザーは次の方法でパブリック インスタント メッセージング接続ユーザーにアクセスできます。

  - IM とプレゼンス

  - パブリック インスタント メッセージング接続の連絡先を Lync クライアント内に表示

  - 連絡先との 1 対 1 の IM 会話

  - Windows Live ユーザーとの音声およびビデオ通話

Lync Server フェデレーションは、Lync Server の展開と他の Office Communications Server 2007 R2 または Lync Server の展開との間の合意を定義します。Lync Server フェデレーションを構成すると、Lync ユーザーは次の方法でフェデレーション ユーザーにアクセスできます。

  - IM とプレゼンス

  - フェデレーションの連絡先を Lync クライアントに作成

XMPP フェデレーションは、XMPP (eXtensible Messaging and Presence Protocol) に基づく外部展開を定義します。XMPP を構成すると、Lync ユーザーは許可された XMPP ドメイン ユーザーに次の方法でアクセスできます。

  - IM およびプレゼンス (1 対 1 のみ)

  - XMPP フェデレーションからの連絡先を Lync クライアントに作成

<div>


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>エッジ サーバー外部フェデレーション、パブリック インスタント メッセージング接続、および XMPP ユーザーの展開プロセス


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>アクセス許可</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既存のエッジ展開に追加するオプションを決める</p></td>
<td><p>トポロジビルダーを実行して、エッジサーバーの設定を編集し、トポロジを作成および公開します。 既存のエッジトポロジによって、中央管理ストアからエッジサーバーへの変更がレプリケートされます。</p></td>
<td><p>Domain Admins グループおよび RTCUniversalServerAdmins グループ。</p>



> [!NOTE]
> ローカル ユーザー グループのメンバーであるアカウントを使用してトポロジを編集できますが、トポロジを公開するには Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーであるアカウントが必要です。

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの構築</a></p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備をする</p></td>
<td><ol>
<li><p>システムの前提条件が適合していることを確認します。</p></li>
<li><p>内部および外部 DNS レコードを構成して、パブリック インスタント メッセージング接続、Lync フェデレーション、および XMPP フェデレーションをサポートします。</p></li>
<li><p>ファイアウォールのポートとプロトコルを構成して、展開するフェデレーションの種類をサポートします。</p></li>
<li><p>パブリック証明書を取得してインストールします。証明書の取得に必要な時間は、どの証明機関 (CA) が証明書を発行するかによって異なります。この時点で、この手順を必ずしも実行する必要はありません。この手順を実行しない場合は、エッジ サーバーの構成時に実行する必要があります。 証明書を取得しないと、エッジ サーバー サービスを開始できません。</p></li>
</ol></td>
<td><p>組織に応じる (一般に、これらの役割は多数のワーク グループと切り離されるため)</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</a></p></td>
</tr>
<tr class="odd">
<td><p>フェデレーション シナリオ用にエッジ サーバーを設定する</p></td>
<td><ol>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジ サーバーにトランスポートするか、レプリケーションを完了できるようにします。</p></li>
<li><p>展開ウィザードを再実行して、フェデレーション用にサポートされているコンポーネントをインストールします。</p></li>
<li><p>エッジ サーバーを構成します。</p></li>
<li><p>各エッジ サーバー用の証明書を要求してインストールします。</p></li>
<li><p>エッジ サーバー サービスを再起動します。</p></li>
</ol></td>
<td><p>Administrators グループ。</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013 での Lync フェデレーションのセットアップ</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセージング接続の設定</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013 での XMPP フェデレーションのセットアップ</a></p></td>
</tr>
<tr class="even">
<td><p>外部ユーザー アクセスのサポートの構成</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルの外部ユーザーアクセスを使用する</p></li>
<li><p>外部アクセス ポリシーを構成して、フェデレーション ユーザーやパブリック ユーザーとの通信を有効します。</p></li>
<li><p>SIP フェデレーション ドメインを構成して、ドメインを許可または禁止します。</p></li>
<li><p>パブリック インスタント メッセージング接続プロバイダーに対して SIP フェデレーション プロバイダーを有効にします。</p></li>
<li><p>XMPP ドメインごとに XMPP フェデレーション パートナーを構成します。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウント。</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザーアクセスのサポートの構成</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013 のパブリックプロバイダーに対するメディアの暗号化の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジ サーバー構成を確認します。</p></td>
<td><p>内部サーバーからのサーバー接続および構成データのレプリケーションを確認します。</p></td>
<td><p>レプリケーションの確認には、RTCUniversalServerAdmins グループ、または CSAdministrator の役割に割り当てられているユーザー アカウントが必要。ユーザー接続の確認には、フェデレーション ユーザーの種類ごとにユーザーが必要。</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジ展開の確認</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 の XMPP 構成の例-Google Talk との XMPP フェデレーション</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


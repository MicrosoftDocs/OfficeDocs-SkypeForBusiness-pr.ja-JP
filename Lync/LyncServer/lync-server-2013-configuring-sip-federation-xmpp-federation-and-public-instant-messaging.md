---
title: SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成
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
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

フェデレーション、パブリックインスタントメッセージング接続、および拡張メッセージングとプレゼンスプロトコル (XMPP) では、フェデレーションユーザーのさまざまなクラスの外部ユーザーを定義しています。 フェデレーションされた Lync Server 展開または XMPP の展開のユーザーは、限定されたサービスのセットにアクセスし、外部展開によって認証されます。 リモートユーザーは、Lync Server 展開のメンバーであり、展開によって提供されるすべてのサービスにアクセスできます。

<div>


> [!NOTE]
> AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。



</div>

パブリックインスタントメッセージング接続は、lync Server クライアントが Lync 2013 を使って、構成済みのパブリックインスタントメッセージングパートナーにアクセスできるようにする特別な種類のフェデレーションです。 現在のパブリックインスタントメッセージング接続パートナーは次のとおりです。

  - <span></span>  
    America Online

  - <span></span>  
    Windows Live

  - <span></span>  
    !\!

パブリックインスタントメッセージングの接続構成を使うと、Lync ユーザーは次の方法でパブリックインスタントメッセージング (im) 接続にアクセスできます。

  - IM とプレゼンス

  - Lync クライアントでのパブリックインスタントメッセージング接続の連絡先の表示

  - 連絡先との IM 会話をする人

  - Windows Live ユーザとの音声通話とビデオ通話

Lync server federation は、Lync Server の展開とその他の Office Communications Server 2007 R2 または Lync Server の展開との間の契約を定義します。 Lync Server のフェデレーション構成により、Lync ユーザーは次の方法でフェデレーションユーザーにアクセスできます。

  - IM とプレゼンス

  - Lync クライアントでのフェデレーションされた連絡先の作成

XMPP フェデレーションは、拡張メッセージングとプレゼンスプロトコルに基づいて外部展開を定義します。 XMPP の構成により、Lync ユーザーは次の方法で許可された XMPP ドメインユーザーにアクセスできます。

  - IM とプレゼンス–人物との連絡のみ

  - Lync クライアントでの XMPP フェデレーション連絡先の作成

<div>


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a>エッジサーバーの外部フェデレーション、パブリックインスタントメッセージング接続、および XMPP ユーザー展開プロセス


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>アクセス許可</th>
<th>ドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>既存のエッジ展開に追加するオプションを決定する</p></td>
<td><p>トポロジビルダーを実行して、エッジサーバーの設定を編集し、トポロジを作成して公開します。 既存のエッジトポロジによって、中央管理ストアからエッジサーバーに変更がレプリケートされます。</p></td>
<td><p>Domain Admins グループと RTCUniversalServerAdmins グループ</p>



> [!NOTE]
> [ローカルユーザー] グループのメンバーであるアカウントを使用してトポロジを編集することはできますが、トポロジを公開するには、Domain Admins グループと RTCUniversalServerAdmins グループのメンバーであるアカウントが必要です。

</td>
<td><p><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 でのエッジおよびディレクターのトポロジの作成</a></p></td>
</tr>
<tr class="even">
<td><p>セットアップの準備をする</p></td>
<td><ol>
<li><p>システムの前提条件が満たされていることを確認します。</p></li>
<li><p>内部と外部の DNS レコードを構成し、パブリックインスタントメッセージング接続、Lync フェデレーション、および XMPP フェデレーションをサポートします。</p></li>
<li><p>展開しているフェデレーションの種類をサポートするために、ファイアウォールでポートおよびプロトコルを構成する</p></li>
<li><p>公開証明書を取得してインストールします。 証明書を取得するために必要な時間は、証明書が発行される証明機関 (CA) によって異なります。 この手順は、展開のこの時点では省略可能です。 この手順をこの時点で実行しない場合は、エッジサーバーの構成中に実行する必要があります。 エッジサーバーサービスは、証明書が取得されるまで開始できません。</p></li>
</ol></td>
<td><p>組織に応じて、通常、これらの役割は多数のワークグループに分割されます。</p></td>
<td><p><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画</a></p></td>
</tr>
<tr class="odd">
<td><p>フェデレーションシナリオ用にエッジサーバーを設定する</p></td>
<td><ol>
<li><p>エクスポートされたトポロジ構成ファイルを各エッジサーバーにトランスポートするか、複製を完了できるようにする</p></li>
<li><p>展開ウィザードを再実行して、フェデレーション用のサポートコンポーネントをインストールする</p></li>
<li><p>エッジサーバーを構成する</p></li>
<li><p>エッジサーバーごとに証明書を要求およびインストールする</p></li>
<li><p>Edge Server サービスを再起動する</p></li>
</ol></td>
<td><p>管理者グループ</p></td>
<td><p><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013 での Lync フェデレーションのセットアップ</a></p>
<p><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセージング接続の設定</a></p>
<p><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013 XMPP フェデレーションのセットアップ</a></p></td>
</tr>
<tr class="even">
<td><p>外部ユーザーアクセスのサポートを構成します。</p></td>
<td><ol>
<li><p>Lync Server コントロールパネルの外部ユーザーアクセスを使用する</p></li>
<li><p>フェデレーションされたユーザーまたはパブリックユーザーとの通信を有効にするための外部アクセスポリシーを構成する</p></li>
<li><p>SIP フェデレーションドメインを構成してドメインを許可またはブロックする</p></li>
<li><p>パブリックインスタントメッセージング接続プロバイダーの SIP フェデレーションプロバイダーを有効にする</p></li>
<li><p>Xmpp ドメインごとに XMPP フェデレーションパートナーを構成する</p></li>
</ol></td>
<td><p>CSAdministrator ロールに割り当てられている RTCUniversalServerAdmins グループまたはユーザーアカウント</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスのサポートの構成</a></p>
<p><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成</a></p></td>
</tr>
<tr class="odd">
<td><p>エッジサーバーの構成を確認する</p></td>
<td><p>内部サーバーからのサーバー接続と構成データのレプリケーションを確認する</p></td>
<td><p>ユーザー接続の確認のために CSAdministrator ロールに割り当てられている複製、RTCUniversalServerAdmins グループ、またはユーザーアカウントを確認するには、フェデレーションユーザーの種類ごとにユーザーを指定します。</p></td>
<td><p><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013 でのエッジの展開の検証</a></p>
<p><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013 での XMPP 構成の例  - Google Talk との XMPP フェデレーション</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


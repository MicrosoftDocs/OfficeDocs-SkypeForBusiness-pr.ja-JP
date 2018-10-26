---
title: 常設チャット サーバーに対する下位互換性の実行
TOCTitle: 常設チャット サーバーに対する下位互換性の実行
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48272098
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 常設チャット サーバーに対する下位互換性の実行

 

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013常設チャット サーバー エンドポイントでは、常設チャット サーバー プールを指す簡易 URL を作成できます。これは、従来のクライアント (Microsoft Office Communications Server 2007 R2グループ チャット サーバーまたは Lync Server 2010、グループ チャット) で役立ちます。従来のクライアントから Lync 2013常設チャットを実行するコンピューターを参照しようとしたときに、ユーザーは手動構成で簡易 URL を入力できるためです。このエンドポイントは 常設チャットでは使用されず、従来のクライアントでのみ必要です。このエンドポイントは、ルームの移行は可能であっても、Lync 2013 クライアントが組織全体に展開されていない暫定期間に役立ちます。Lync 2010グループ チャット (クライアント) を実行しているユーザーは、常設チャット サーバーバック エンド サーバーに引き続き接続できます。

複数の 常設チャット サーバー エンドポイントを作成する必要はありません。必要なエンドポイントは、常設チャット サーバー プールごとに 1 つだけです。管理者は複数のエンドポイント (プールごとに 1 つ) を作成できますが、従来のクライアントでは一度に 1 つのプールへの接続しか構成できません。通常の一般的なシナリオでは、従来の展開にはプールは 1 つしかありません。通常、新しい展開では、このプールが新しい Lync Server 2013 に移行され、必要に応じて新しい 常設チャット サーバー プール プールが追加されます。

一般的なシナリオでは、通常、次のパターンをたどります。

  - ユーザーを 1 つの Lync Server 2010、グループ チャット プールで管理し、Lync 2010 グループ チャット クライアントは既知のユーザー (既定の sip:ocschat@ *\<domainName\>* .com など) を使用してそのプールに接続します。ユーザーは SIP 対応の Active Directory ドメイン サービス であり、参照サービスはこれらのユーザーに登録して着信要求を受信します。

  - その後、Lync Server 2013常設チャット サーバーおよび 常設チャット サーバー プールをインストールします。

  - ユーザーが通常オフラインになる時間帯 (週末など) に次の操作を実行します。
    
      - Lync Server 2010、グループ チャットをオフにします。
    
      - Lync Server 2010、グループ チャット プールから Lync Server 2013常設チャット サーバー プールにデータを移行します。
    
      - Active Directory ドメイン サービス から既知のユーザーを削除します。
    
      - 前の手順で削除した既知のユーザーと同じ SIP URI を持つ新しいレガシ エンドポイントを作成します。
    
      - Lync Server 2013常設チャット サーバー を起動します。

  - ユーザーは、Lync 2010 グループ チャット (クライアント) を使用して再ログオンし、構成を変更する必要なくデータに接続します。

  - その後で、Lync Server 2010、グループ チャットの使用を停止できます。その後、Lync Server 2013常設チャット サーバーを展開し、新しい Lync Server 2013常設チャット サーバー プールをインストールできます。

Lync Server 2010、グループ チャットから Lync Server 2013常設チャット サーバーへの移行の詳細については、「[Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。

下位互換を実行するには (従来の グループ チャット プール クライアントが使用できる、常設チャット サーバー プールを指す 常設チャット サーバー エンドポイントを作成するには)、次のコマンドを実行します。

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

次に、常設チャット クライアントを構成して、その SIP アドレスをクライアントの連絡先オブジェクトとして使用します。SIP アドレスは、**New-CsPersistentChatEndpoint** コマンドレットで特定の 常設チャット サーバー プールに対して作成されます。

Windows PowerShell コマンドライン インターフェイスを使用して 常設チャット サーバー エンドポイントを追加する場合は、次の例を参考にしてください。この例では、プールの完全修飾ドメイン名 (FQDN) が "pcpool.contoso.com" である "contoso.com" トポロジで "persistentchat" という名前の連絡先オブジェクトを構成します。

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

## 関連項目

#### 概念

[Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)


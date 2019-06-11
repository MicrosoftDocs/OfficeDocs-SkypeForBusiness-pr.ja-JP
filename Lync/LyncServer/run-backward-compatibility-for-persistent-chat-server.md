---
title: 常設チャット サーバーに対する下位互換性の実行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>常設チャット サーバーに対する下位互換性の実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Lync Server 2013、常設チャットサーバーのエンドポイントは、常設チャットサーバープールを示す簡単な URL を作成するための手段を提供します。 これは、レガシクライアント (Microsoft Office Communications Server 2007 R2 グループチャットサーバーまたは Lync Server 2010、グループチャット) で便利です。ユーザーは従来のクライアントを Lync 2013 を実行しているコンピューターにポイントしようとして、手動構成で簡単な URL を入力できます。常設チャット。 このエンドポイントは常設チャットで使用されておらず、レガシクライアントでのみ必要です。 これは、会議室が移行される中間的な期間内に、Lync 2013 クライアントが組織全体に展開されていない場合に便利です。 Lync 2010 グループチャット (クライアント) を実行しているユーザーは、引き続き常設チャットサーバーバックエンドサーバーに接続できます。

複数の常設チャットサーバーのエンドポイントを作成する必要はありません。常設チャットサーバープールごとに1つだけ必要です。 管理者は複数のエンドポイントを作成できますが (1 つのプールあたり1つ)、従来のクライアントは一度に1つのプールにしか接続できないように構成できます。 通常またはメインストリームのシナリオでは、従来の展開は1つのプールのみになります。 新しい展開では、通常、プールは新しい Lync Server 2013 に移行され、追加の常設チャットサーバープールが追加されることがあります。

このメインストリームシナリオは一般的に、次のパターンに従います。

  - 1人の Lync Server 2010、グループチャットプール、Lync 2010 グループチャットクライアントを使って、ユーザーを管理するには、既知のユーザー (既定の sip: ocの @\<domainName\>、または類似したユーザー) を使用します。 ユーザーは SIP 対応の Active Directory ドメインサービスであり、参照サービスは、着信要求を受信するためにそれを登録します。

  - 続いて、Lync Server 2013 常設チャットサーバーと常設チャットサーバープールをインストールします。

  - 通常、ユーザーがオフラインになっている時間 (例: 週末):
    
      - Lync Server 2010、グループチャットをオフにします。
    
      - Lync Server 2010 からデータを移行するには、グループチャットプールを Lync Server 2013 常設チャットサーバープールに移動します。
    
      - Active Directory ドメインサービスから既知のユーザーを削除します。
    
      - 以前に削除した既知のユーザーと同じ SIP URI を持つ新しい*従来のエンドポイント*を作成します。
    
      - Lync Server 2013 の常設チャットサーバーを起動します。

  - ユーザーは、設定を変更せずに、Lync 2010 グループチャット (クライアント) を使ってもう一度ログインし、データに接続します。

  - 後で、Lync Server 2010、グループチャットの使用を停止することができます。 続いて、Lync Server 2013、常設チャットサーバーを展開して、新しい Lync Server 2013 常設チャットサーバープールをインストールすることができます。

Lync Server 2010 からの移行の詳細については、グループチャットから Lync Server 2013、常設チャットサーバーに移行する方法については、「 [Lync server 2010、グループチャット、または Office Communications server 2007 R2 グループチャットから Lync server 2013、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。

下位互換性を実行するには (従来のグループチャットプールクライアントで使用できる常設チャットサーバープールをポイントする常設チャットサーバーのエンドポイントを作成するには) 次の操作を行います。

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

次に、その SIP アドレスを連絡先オブジェクトとして使用するように常設チャットクライアントを構成します。 SIP アドレスは、特定の常設チャットサーバープール用の**CsPersistentChatEndpoint**コマンドレットを使用して作成されます。

Windows PowerShell コマンドラインインターフェイスを使用して常設チャットサーバーのエンドポイントを追加するには、次の例を参考にしてください。 この場合、プールの完全修飾ドメイン名 (FQDN) が "pcpool.contoso.com" である "contoso.com" トポロジで、"persistentchat" という名前の連絡先オブジェクトを設定します。

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


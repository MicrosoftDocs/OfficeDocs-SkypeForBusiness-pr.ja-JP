---
title: 常設チャットサーバーの下位互換性を実行する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329415e7bae43bbbfd3a77da39e99049f4fe617e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>常設チャットサーバーの下位互換性を実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Lync Server 2013、常設チャットサーバーエンドポイントは、常設チャットサーバープールを指す簡単な URL を作成する方法を提供します。 これはレガシクライアント (Microsoft Office Communications Server 2007 R2 グループチャットサーバーまたは Lync Server 2010、グループチャット) の場合に便利です。これは、ユーザーがレガシクライアントを Lync 2013 を実行しているコンピューターに接続しようとしているときに、手動構成で簡単な URL を入力できるためです。常設チャット。 このエンドポイントは常設チャットでは使用されていません。レガシークライアントにのみ必要になります。 これは、会議室が移行される中間期間では便利ですが、Lync 2013 クライアントは組織全体に展開されていません。 Lync 2010 グループチャット (クライアント) を実行しているユーザーは、引き続き常設チャットサーバーのバックエンドサーバーに接続できます。

複数の常設チャットサーバーのエンドポイントを作成する必要はありません。常設チャットサーバープールごとに1つだけ必要です。 管理者は複数のエンドポイント (プールごとに1つ) を作成できますが、従来のクライアントは一度に1つのプールにのみ接続するように構成できます。 通常または主流のシナリオでは、従来の展開は1つのプールのみになります。 新しい展開では、通常、そのプールを新しい Lync Server 2013 に移行し、別の新しい常設チャットサーバープールを追加することがあります。

一般的なシナリオでは、通常、次のパターンをたどります。

  - 1つの Lync Server 2010、グループチャットプール、および Lync 2010 グループチャットクライアントを使用してユーザーを管理するには、既知のユーザー (既定の sip: ocschat@\<domainName\>) を使用して、そのプールに接続します。 ユーザーは、SIP が有効な Active Directory ドメインサービスであり、参照サービスが着信要求を受信するために登録します。

  - その後、Lync Server 2013 常設チャットサーバーと常設チャットサーバープールをインストールします。

  - ユーザーが通常オフラインになる時間帯 (週末など) に次の操作を実行します。
    
      - Lync Server 2010、グループチャットをオフにします。
    
      - Lync Server 2010 のグループチャットプールから Lync Server 2013 常設チャットサーバープールにデータを移行します。
    
      - Active Directory ドメインサービスから既知のユーザーを削除します。
    
      - 前の手順で削除した既知のユーザーと同じ SIP URI を持つ新しいレガシ エンドポイントを作成します。**
    
      - Lync Server 2013、常設チャットサーバーを起動します。

  - ユーザーは、Lync 2010 グループチャット (クライアント) を使用してもう一度ログオンし、構成を変更することなくデータに接続します。

  - 後で、Lync Server 2010 のグループチャットを使用停止にすることができます。 その後、Lync Server 2013、常設チャットサーバーを展開し、新しい Lync Server 2013 常設チャットサーバープールをインストールすることができます。

Lync Server 2010 からの移行の詳細については、「グループチャットから Lync Server 2013、常設チャットサーバーへの移行」を参照してください。「 [Lync server 2010、グループチャットまたは Office Communications server の 2007 R2 グループチャットから lync 2013 server への移行、常設チャットサーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)」を参照してください。

下位互換性を実行するには (従来のグループチャットプールクライアントが使用できる常設チャットサーバープールをポイントする常設チャットサーバーエンドポイントを作成するため):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

次に、その SIP アドレスを連絡先オブジェクトとして使用するように常設チャットクライアントを構成します。 SIP アドレスは、特定の常設チャットサーバープール用の**new-cspersistentchatendpoint**コマンドレットを使用して作成されます。

Windows PowerShell コマンドラインインターフェイスを使用して常設チャットサーバーエンドポイントを追加するには、次の例を検討してください。 この例では、プールの完全修飾ドメイン名 (FQDN) が "pcpool.contoso.com" である "contoso.com" トポロジで "persistentchat" という名前の連絡先オブジェクトを構成します。

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


---
title: 'Lync Server 2013: 外部ユーザーアクセスの新機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e85c9e83a6dde06c7c091241bea903a3ddd1d813
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 の外部ユーザーアクセスの新機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-17_

Lync Server 2013 には、ユーザーの機能や通信方法を拡張する新機能が導入されています。 また、Lync Server 2013 では、組織で使用できるサービスをより適切に統合および拡張するための既存のサービスへの変更が導入されています。 Lync Server 2013 エッジサーバーサービスの計画と展開に影響する可能性のある変更の概要を次に示します。

  - **Ipv6 アドレス指定**   のサポート Lync server 2013 は、すべてのエッジサーバーサービスの ipv6 アドレスをサポートしています。 Windows Server の構成を使用してインターフェイスの IPv6 アドレスを指定した場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成で IPv6 アドレスを使用できます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 での IPv6 アドレスの使用は、組織が展開するルーターとファイアウォールでの IPv6 のサポート、およびインターネットサービスプロバイダーによるサポートに依存します。

    
    </div>

  - **拡張可能なメッセージングおよびプレゼンスプロトコル (xmpp)**   Lync Server 2013 には、完全に統合された xmpp プロキシ (エッジサーバーに展開される) と、フロントエンドサーバーに展開された xmpp ゲートウェイが導入されています。 オプションのコンポーネントとして XMPP フェデレーションを展開できます。 XMPP プロキシと XMPP ゲートウェイを追加して構成すると、Microsoft Lync 2013 ユーザーがインスタントメッセージング (IM) とプレゼンスの XMPP ベースのパートナーから連絡先を追加できるようになります。
    
    <div>
    

    > [!NOTE]  
    > 現時点では、Lync Server 2013 の XMPP サービスは、Lync クライアントと XMPP ベースの連絡先間でインスタントメッセージングとプレゼンスを提供するだけです。

    
    </div>

  - **Mobile クライアント**   用のモビリティサービス lync server 2010 のモバイルサービス、lync server 2013 のモビリティサービスでは、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して、携帯電話やタブレットデバイスの Microsoft Lync mobile クライアントが、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。
    
    <div>
    

    > [!NOTE]  
    > モビリティ サービスは、フロントエンド サーバーに展開されたリバース プロキシと公開されたサービスを使用します。 エッジ サーバーの変更は必要ありません。

    
    </div>

  - **ディレクターはオプションの役割**   Lync server 2013 トポロジ内のディレクターサーバーの役割は変更されていません。 fea-director-server-roleが推奨される役割からオプションの役割に変更されることにより、fea-director-server-roleの価値が下がるというわけではありません。 推奨されている役割からオプションの役割にディレクターを変更しても、ディレクターの値は減少しませんが、サーバーの数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) の要件が減少することが強調されます。機能の侵害。 フロントエンドサーバーは、提供されるサービスに影響を与えることなく、ディレクターと同じジョブを実行できるため、必要に応じて、ディレクターを展開することもできます。 フロントエンドサーバーによって同じサービスが提供されるという確信を持って、ディレクターを安全に除外することができます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での IPv6 の計画と構成](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


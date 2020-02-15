---
title: 'Lync Server 2013: 外部ユーザーアクセスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed3a616fb9bcf7d33819c3bee68dbe375954d02b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Lync Server 2013 の外部ユーザーアクセスの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このドキュメントでは、*外部ユーザー*という用語を使用して、ファイアウォールの外側から lync Server 2013 および lync 2013 ユーザーと通信する大規模なユーザーのカテゴリを定義します。 Lync Server 2013 と内部ユーザーとの通信を承認できる外部ユーザー (つまり、ファイアウォールの内側から Lync Server にサインインしているユーザー) には、以下のものが含まれます。

  - **リモートユーザー**   組織のユーザーが、ファイアウォールの外側から Lync Server にサインインしている。

  - **フェデレーションユーザー**   : lync server 2010、lync server 2013、Office Communications server 2007 R2 などの信頼できる顧客またはパートナー組織のアカウントを持つユーザー。 また、フェデレーションユーザーは、エッジサーバー上の XMPP プロキシとフロントエンドサーバーまたはプール上の xmpp ゲートウェイによって、拡張可能なメッセージングとプレゼンスプロトコル (XMPP) を使用して、定義されたパートナー組織のメンバーになることもできます。 フェデレーションと呼ばれる定義済みの信頼関係は、Active Directory ドメインサービスの信頼関係に関連していないか、または依存していません。
    
    <div>
    

    > [!NOTE]  
    > AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。

    
    </div>

  - ****   パブリックインスタントメッセージング接続ユーザーがパブリックインスタントメッセージング接続サービス (Windows Live、Yahoo) を介して確立した連絡先。\! および AOL)。

  - **モバイルユーザー**   組織のメンバーであり、スマートフォンまたは Lync Mobile クライアントを実行しているタブレットを使用するユーザーは、内部展開にサインインして、他のユーザークラスと通信することができます。 モバイルユーザーは、リバースプロキシを介して公開された mobility services を使用して内部展開にアクセスします。 Lync Mobile で利用できる機能の詳細については、「」のモバイルクライアント[http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)の比較表を参照してください。

  - **匿名ユーザー**   組織の Active Directory ドメインサービスまたはサポートされているフェデレーションドメインでユーザーアカウントを持っていないが、オンプレミスの会議にリモートで参加する招待を受け取っているユーザー。

エッジ展開は、次の種類の通信に対する外部アクセスを提供します。

  - **Im およびプレゼンス**   権限がある外部ユーザーは、im 会話や会議に参加でき、互いのプレゼンス状態に関する情報を取得することができます。 パブリック IM サービスプロバイダーのユーザーは、組織内の個々の Lync Server ユーザーとの IM 会話に参加し、プレゼンス情報にアクセスできますが、Lync Server を使用して IM マルチパーティ会議に参加することはできません。 これは、厳密にピアツーピア通信です。 ファイル転送は、パブリック IM サービスプロバイダーのユーザーに対してはサポートされていません。ピアツーピア通信の音声ビデオは、Windows Messenger 2011 ユーザーに対してサポートされていますが、パブリック IM サービスプロバイダーの他のユーザーに対してはサポートされていません。
    
    SIP と XMPP の両方のプロトコルがサポートされています。 XMPP のサービスを提供するには、「 [Lync Server 2013 での SIP、XMPP フェデレーション、パブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)」を参照してください。

  - **Web 会議**   の承認済みの外部ユーザーは、Lync Server の展開でホストされている会議に参加できます。 リモート ユーザー、フェデレーション ユーザー、および匿名ユーザーの Web 会議への参加は許可することができますが、パブリック IM ユーザーは会議に参加できません。 選択するオプションに応じて、Web 会議への参加が許可されているユーザーは、デスクトップおよびアプリケーションの共有に参加でき、会議の開催者または発表者の役を務めることができます。

  - ****   音声ビデオ会議の承認済みの外部ユーザーは、Lync Server 展開でホストされている音声ビデオ会議に参加できます。 ピアツーピア通信での音声/ビデオは、Windows Messenger 2011 ユーザーに対してサポートされていますが、パブリック IM サービスプロバイダーの他のユーザーに対してはサポートされていません。

通信を制御するために、1つまたは複数のポリシーを構成して、組織内外のユーザーが相互に通信する方法を定義することができます。 また、外部ユーザーとの通信を制御するために、個々の内部ユーザーまたは特定の種類の外部ユーザーに対して、設定を構成し、ポリシーを適用することができます。

外部アクセスを提供するために使用される Lync Server 2013 の役割:

**エッジサーバー**   エッジサーバーは、IM、プレゼンス、会議、音声ビデオ、その他のメディア (たとえば、ファイル転送) サービスへの外部アクセスを許可するサービスを実行するサーバーまたはサーバーのプールです。 必要に応じて、他の Lync Server または Office Communications Server 2007 R2 展開やその他の XMPP 展開とフェデレーションされるようにエッジサーバーを構成することができます。 オプションのパブリック IM 接続機能は、エッジサーバーを使用して有効にし、構成します。

**ディレクター**   ディレクターは、ユーザーの要求を事前認証し、要求をユーザーのホームフロントエンドサーバーまたはフロントエンドプールにルーティングする、Lync server 2013 ディレクターの役割を実行するオプションのサーバーまたはサーバープールです。ただし、ユーザーアカウントをホームにすることはありません。

**リバースプロキシ**   リバースプロキシは、内部ネットワークで利用可能なリソースを公開し、発行されたリソースからクライアントの情報を取得する、専用のサーバーの一般的な用語です。 Lync Server 2013 はリバースプロキシを使用して、会議会議、会議参加場所、アドレス帳、配布リストの拡張、会議コンテンツのダウンロード、デバイスの更新、モビリティサービスなど、さまざまな機能を公開します。 必要なリソースの場所を公開するための要件を満たすことができるリバースプロキシを使用できます。 Microsoft Forefront Threat Management Gateway (TMG) 2010 は、必要な公開ルールを示すための例として使用されていますが、Forefront TMG 2010 は必要ありません。

<div>


> [!IMPORTANT]  
> Lync Server 2013 は、IPv4 と IPv6 の両方をサポートしています。 Windows Server&nbsp;2008&nbsp;r2、windows Server 2012、および windows server 2012 R2 は、IPv4 と IPv6 の両方を同時に使用できるデュアルスタックを使用します。 これは、IPv4 から IPv6 への展開の移行の性質上、重要です。 IPv4 は、一部の分野ではサポートされており、他の領域では IPv6 を使用することができます。 これは、インターネットと内部の展開に関して特に重要です。 外部クライアントは、モビリティ、会議、アドレス帳のダウンロードなどのサービスを使用するために、リバースプロキシを介して通信する必要があります。 現時点では、Forefront Threat Management Gateway 2010 および Internet Security and アクセラレーションサーバー2006は、展開されているオペレーティングシステムのバージョンに関係なく、IPv6 アドレスをサポートしていません。 外部クライアントに関連する場合は、IPv6 と IPv4 の使用に関して計画する必要があります。



</div>

</div>

<span> </span>

</div>

</div>

</div>


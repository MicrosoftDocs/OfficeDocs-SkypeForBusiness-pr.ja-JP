---
title: 'Lync Server 2013: モビリティのトポロジとコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3681cc93ef3b382e586d79c0cd92646d0198dac0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 でのモビリティのトポロジとコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

モバイルデバイスで Lync mobile アプリケーションをサポートするために、2013 Lync server 2013 Mcx Mobility Service、Lync Server 2013 自動検出サービス、Lync Server 2013 プッシュ通知サービスの3つのサービスが用意されています。 Lync Server 2013 の累積的な更新プログラム: 2 月2013は、統合コミュニケーション Web API または UCWA の使用により、Lync 2013 Mobile クライアントのための無料のサービスが追加されています。 このセクションでは、これらのコンポーネントについて簡単に説明し、モビリティをサポートする Lync Server 2013 トポロジを示します。

<div>


> [!NOTE]  
> モビリティ サービスは、ハイブリッド展開でも利用できます。 ユーザーが常時オンラインである場合はモビリティをサポートするためのサービスを展開する必要はありません。 モバイルユーザーがオンライン id を検索できるようにするには、自動検出サービスの設定を定義する必要があります。



</div>

<div>


> [!IMPORTANT]  
> 外部ユーザーの接続を計画している場合 (フェデレーション、外部ユーザーアクセス、またはモビリティ機能など)、Standard Edition サーバーとフロントエンドサーバーまたはフロントエンドプールでエッジサーバーを使用する必要があります。 Standard Edition サーバーとフロントエンドサーバーまたはフロントエンドプールに、外部ユーザーが内部展開にアクセスできるようにするため、または内部展開で外部ユーザーと通信するために必要なコンポーネントがありません。 外部ユーザーを共同作業するか、モビリティを含む内部ユーザーと通信するすべてのシナリオについて、少なくとも1つのエッジサーバーと1つのリバースプロキシを展開する必要があります。<BR><EM>プッシュ通知</EM>では、プッシュ通知クリアリングハウス (pnch) をホストする Lync Online サービスへのフェデレーションの種類を使用します。 プッシュ通知は、モバイルデバイスが非アクティブな場合に、アプリケーションによって Apple の iPhone、iPad、および Windows Phone にプッシュされるサウンド通知、画面上の警告 (テキスト)、バッジを表します。 PNCH は、Lync Server からプッシュ通知を受信します。 PNCH がメッセージの通知を受信すると、PNCH は、メッセージが意図されているモバイルクライアントに基づいて、Apple プッシュ通知サービスまたは Lync Server 2013 プッシュ通知サービスのいずれかを介してモバイルクライアントに通知を転送します。 PNCH は、これらのモバイル クライアントにとって必須のサービスです。 Lync Online とのフェデレーションを行うために、PNCH はエッジサーバーと証明書を使用して、機密性と認証、ポリシー、および適切に構成されたドメインネームシステム (DNS) レコードを確保します。 Nokia Symbian および Android ベースの Lync Mobile クライアントでは、PNCH は使用されません。 エッジサーバーの計画および展開の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">lync server 2013 での外部ユーザーアクセスの計画</A>」および「 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。<BR>Lync Server 2013 用の累積的な更新プログラムで導入された、lync 2013 モバイルクライアント (Lync Server 用): 2 月2013は、プッシュ通知またはプッシュ通知クリアリングハウス (PNCH) を使用しなくなりました。 Windows Phone の Lync 2013 モバイルクライアントは、引き続きプッシュ通知と (PNCH) を使用します。



</div>

<div>

## <a name="mobility-components"></a>モビリティ コンポーネント

モビリティをサポートするサービスは次のとおりです。

  - **Lync server 2013 統合コミュニケーション Web API (ucwa)**   lync server 2013 のモバイルおよび Web クライアントとのリアルタイム通信のサービスを提供します。 Lync Server 2013 の累積的な更新プログラム (2013 年2月) をフロントエンドサーバーとディレクターに展開すると、インストール時に内部および外部の web サービス (Ucwa) に仮想ディレクトリが作成されます。 Ucwa 仮想ディレクトリの一部である web コンポーネントは、UCWA が有効なクライアントからの呼び出しを受け付けます。 クライアントアプリは、プレゼンス、連絡先、インスタントメッセージング、VoIP、ビデオ会議、およびコラボレーションのための REST インターフェイスを介して通信します。 UCWA は、P-GET ベースのチャネルを使用して、着信呼び出し、インスタントメッセージの受信、クライアントアプリへのメッセージなどのイベントを送信します。
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM>または表現的な状態転送は、多くのフォームで広く採用されており、一般の Web サービスの要件に適している分散システムのソフトウェアアーキテクチャスタイルです。

    
    </div>

  - **Lync Server 2013 Mobility service (mcx)**   このサービスは、モバイルデバイスでのインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートします。 Mobility Service は、各プールのすべてのフロントエンドサーバーにインストールされ、モバイルデバイスで Lync 機能をサポートします。 Lync Server 2013 をインストールすると、内部 web サイトとフロントエンドサーバー上の外部 web サイトの両方に新しい仮想ディレクトリ (Mcx) が作成されます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013 の累積的な更新プログラム (Lync server 2013): 2 月2013は、Lync Server 2010 用の累積的な更新プログラムで導入された Mobility service の両方をサポートしています。 11 2011 月 (一般に Mcx)、UCWA web コンポーネント。 これら2つの mobility service の組み合わせにより、lync Server 2013 で lync 2010 mobile および Lync 2013 Mobile クライアントを使用するユーザーが相互運用性を提供し、使用することができます。

    
    </div>

  - **Lync server 2013 自動検出サービス**   このサービスは、ユーザーの場所を識別し、モバイルデバイスやその他の lync クライアントが、ネットワークの場所に関係なく、lync Server 2013 Web サービスの内部 url と外部 url、mcx または ucwa の url などのリソースを検索できるようにします。 自動検出では、ハードコードされたホスト名 (ネットワーク内のユーザーの場合は lyncdiscoverinternal、ネットワーク外部のユーザーの場合は lyncdiscover、ユーザーの SIP ドメイン) を使用します。 HTTP または HTTPS のどちらかを使用するクライアント接続をサポートします。
    
    自動検出サービスは、すべてのフロントエンドサーバーと、各プールのすべてのディレクターにインストールされます。これは、モバイルデバイスで Lync 機能をサポートするためのものです。 自動検出サービスをインストールすると、フロントエンドサーバーとディレクターの両方で、内部 web サイトと外部 web サイトの両方に新しい仮想ディレクトリ (自動検出) が作成されます。
    
    <div>
    

    > [!NOTE]  
    > 自動検出サービスは、モバイルクライアントサービスを提供する際に重要なコンポーネントであるため、ここにリストされています。 Lync Server 2013 での自動検出の役割は、すべてのクライアントにサービスを提供するように拡張されています。 自動検出サービスの計画の詳細については、「 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013 での自動検出の計画</A>」を参照してください。

    
    </div>

  - **プッシュ通知サービス**   このサービスは、Lync Online データセンターにあるクラウドベースのサービスです。 サポートされている Apple iOS デバイスまたは Windows Phone の Lync モバイルアプリケーションが非アクティブな場合、新しいインスタントメッセージング (IM) 招待、不在着信メッセージ、不在着信、ボイスメールなどの新しいイベントに応答することはできません。これらのデバイスではサポートされていません。バックグラウンドで実行されているモバイルアプリケーション。 このような場合、新しいイベント (*プッシュ通知*と呼ばれる) の通知がモバイルデバイスに送信されます。 Mobility Service は通知をクラウドベースのプッシュ通知サービスに送信します。これにより、Apple Push Notification Service (APNS) (サポートされている Apple iOS デバイスの場合) または Microsoft プッシュ通知サービス (MPNS) に通知が送信されます。) (Windows Phone の場合) をクリックすると、モバイルデバイスに送信されます。 その後、ユーザーはモバイルデバイスで通知に応答して、アプリケーションをアクティブにすることができます。
    
    Apple および Windows Phone デバイス上の Lync 2010 Mobile は、プッシュ通知を使用します。 Lync Server 2013 用の累積的な更新プログラムで導入された、lync 2013 モバイルクライアント (Lync Server 用): 2 月2013は、プッシュ通知またはプッシュ通知クリアリングハウス (PNCH) を使用しなくなりました。

次の図は、UCWA および Lync 2013 モバイルクライアントを使用する Lync Server 2013 トポロジ内でプッシュ通知サービスがどのように配置されるかを示しています。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Lync Server 2010 の累積的な更新プログラム (2011 年11月) で導入された Mcx サービスは、Lync 2010 Mobile クライアントにサービスを提供します。 次の図は、Mcx および Lync 2010 モバイルクライアントを使用するトポロジに適用されるプッシュ通知サービスを示しています。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 の累積的な更新プログラムの適用: 2 月2013は、次のトポロジで Lync 2013 Mobile クライアント機能のモビリティをサポートするために UCWA web コンポーネントを追加します。

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

エッジサーバーは、Lync Server 2010 エッジサーバーにすることができます。

Lync server 2013 の Lync Server 2013 の累積的な更新プログラムを適用せずに展開する場合: 2 月2013は Mcx Mobility Service を使用し、Lync 2010 Mobile に対してのみサービスを提供することができます。

<div>


> [!IMPORTANT]  
> Mobility Service は、2つのネットワークインターフェイスを使用する仲介サーバーの役割と併置されたフロントエンドサーバーでサポートされていますが、インターフェイスを構成するために適切な手順を実行する必要があります。 仲介サーバーとして通信する特定のインターフェイスに IP アドレスを割り当てる必要があります。また、フロントエンドサーバーとして通信するネットワークインターフェイスの IP アドレスも割り当てる必要があります。 トポロジビルダーでは、[<STRONG>すべての構成済み ip アドレスを使用</STRONG>する] ではなく、各サービスの正しい ip アドレスを選択することで、トポロジビルダーでこの操作を行うことができます。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)  
[Lync Server 2013 での自動検出の計画](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


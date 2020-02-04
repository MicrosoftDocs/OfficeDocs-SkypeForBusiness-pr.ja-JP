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
ms.openlocfilehash: 739deecf47e25e57ca0175c29a2721e509f8dbe2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 のモビリティのトポロジとコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync server 2013 には、モバイルデバイスでの Lync モバイルアプリケーションのサポートについて、lync Server 2013 Mcx Mobility Service、Lync Server 2013 自動検出サービス、Lync Server 2013 プッシュ通知サービスという3つのサービスが用意されています。 Lync Server 2013 向けの累積的な更新プログラム: 2013 年2月に、Lync 2013 モバイルクライアント向けの無料のサービスが追加されました。ユニファイドコミュニケーション Web API、または UCWA を使用したモビリティサポート。 このセクションでは、これらのコンポーネントについて簡単に説明し、モバイル機能をサポートする Lync Server 2013 トポロジを示します。

<div>


> [!NOTE]  
> モバイルサービスは、ハイブリッド展開でも利用できます。 ユーザーがオンラインになっている場合、モバイル機能をサポートするためにサービスを展開する必要はありません。 モバイルユーザーがオンライン id を見つけることができるようにするには、自動検出サービスの設定を定義する必要があります。



</div>

<div>


> [!IMPORTANT]  
> 外部ユーザー接続 (フェデレーション、外部ユーザーアクセス、モバイル機能など) を計画している場合は、Standard Edition server と、フロントエンドサーバーまたはフロントエンドプールでエッジサーバーを使用する必要があります。 Standard Edition server とフロントエンドサーバーまたはフロントエンドプールには、外部ユーザーが内部展開にアクセスすること、または外部ユーザーとの通信を可能にするために必要なコンポーネントがありません。 外部ユーザーが共同作業しているか、モバイルを含む内部ユーザーと通信するすべてのシナリオでは、少なくとも1つのエッジサーバーと1つの逆プロキシを展開する必要があります。<BR><EM>プッシュ通知</EM>では、フェデレーションの種類を Lync Online サービスに使用します。これは、プッシュ通知のクリアリングハウス (pnch) をホストします。 プッシュ通知とは、モバイルデバイスが非アクティブになっているときに、アプリケーションから Apple iPhone、iPad、Windows Phone にプッシュされるサウンド通知、画面上の通知 (テキスト)、バッジを指します。 PNCH Lync Server からプッシュ通知を受信します。 PNCH がメッセージの通知を受信すると、PNCH は、メッセージが意図されているモバイルクライアントに基づいて、Apple Push Notification Services または Lync Server 2013 プッシュ通知サービスを通じてモバイルクライアントに通知を転送します。 PNCH は、これらのモバイルクライアントに必要なサービスです。 Lync Online にフェデレーションを行うために、PNCH はエッジサーバーと証明書を使用して、機密性と認証、ポリシー、適切に構成された domain name system (DNS) レコードを確認します。 Nokia Symbian および Android ベースの Lync モバイルクライアントでは、PNCH は使用されません。 エッジサーバーの計画と展開の詳細については、「 <A href="lync-server-2013-planning-for-external-user-access.md">Lync server 2013 での外部ユーザーアクセスの計画</A>」および「 <A href="lync-server-2013-deploying-external-user-access.md">lync server 2013 での外部ユーザーアクセスの展開</A>」を参照してください。<BR>Apple デバイスの Lync 2013 モバイルクライアントは、Lync Server 2013 の累積更新プログラムで導入されました。2013年2月以降、プッシュ通知またはプッシュ通知のクリアリングハウス (PNCH) は使用されなくなりました。 Windows Phone 上の Lync 2013 モバイルクライアントでも、プッシュ通知と (PNCH) が使用されます。



</div>

<div>

## <a name="mobility-components"></a>モバイルコンポーネント

モバイル機能をサポートするサービスは次のとおりです。

  - **Lync server 2013 ユニファイドコミュニケーション Web API (ucwa)**   では、lync server 2013 のモバイルおよび Web クライアントとのリアルタイム通信のサービスを提供します。 Lync Server 2013 の累積的な更新プログラムを展開すると、2013年2月のフロントエンドサーバーとディレクターに、インストールにより、内部と外部の web サービス (Ucwa) に仮想ディレクトリが作成されます。 Ucwa 仮想ディレクトリの一部である web コンポーネントは、UCWA 対応クライアントからの呼び出しを受け入れます。 クライアントアプリは、プレゼンス、連絡先、インスタントメッセージング、VoIP、ビデオ会議、共同作業のために REST インターフェイスを介して通信します。 UCWA は、P-GET ベースのチャネルを使って、着信通話、インスタントメッセージの受信、クライアントアプリへのメッセージなどのイベントを送信します。
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM>または表現は、さまざまな形式で広く採用されている分散システム向けのソフトウェアアーキテクチャスタイルであり、一般の Web サービスの要件にも適しています。

    
    </div>

  - **Lync Server 2013 モビリティサービス (mcx)**   このサービスは、モバイルデバイスでのインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートします。 モバイルデバイスで Lync 機能をサポートするには、各プールの各フロントエンドサーバーにモビリティサービスがインストールされます。 Lync Server 2013 をインストールすると、内部 web サイトとフロントエンドサーバー上の外部 web サイトの両方に新しい仮想ディレクトリ (Mcx) が作成されます。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013 の累積更新プログラムを含む lync server 2013: 年2月2013では、Lync Server 2010 の累積的な更新プログラムで導入されたモビリティサービスの両方がサポートされます。11月2011、一般的には Mcx、UCWA web コンポーネント。 この2つのモバイルサービスを組み合わせることで、lync 2010 Mobile クライアントと lync 2013 モバイルクライアントを使用するユーザーは、Lync Server 2013 で相互運用性と使用を行うことができます。

    
    </div>

  - **Lync server 2013 自動検出サービス**   このサービスは、ユーザーの場所を特定し、ネットワークの場所に関係なく、モバイルデバイスや他の lync クライアントがリソース (lync Server 2013 Web サービスの内部および外部 url、mcx または ucwa の url など) を特定できるようにします。 自動検出では、ハードコーディングされたホスト名 (ネットワーク内のユーザー向けの lyncdiscover、ネットワーク外のユーザー向けの lyncdiscoverinternal、ユーザーの SIP ドメイン) が使用されます。 HTTP または HTTPS を使用しているクライアント接続をサポートします。
    
    自動検出サービスは、各フロントエンドサーバーにインストールされ、モバイルデバイスで Lync 機能をサポートする各プールの各ディレクターにインストールされます。 自動検出サービスをインストールすると、フロントエンドサーバーとディレクターの両方で、内部 web サイトと外部 web サイトの両方に新しい仮想ディレクトリ (自動検出) が作成されます。
    
    <div>
    

    > [!NOTE]  
    > 自動検出サービスは、モバイルクライアントサービスを提供するときに重要なコンポーネントであるため、ここに記載されています。 Lync Server 2013 での自動検出の役割は、すべてのクライアントに対してサービスを提供するために拡張されています。 自動検出サービスの計画について詳しくは、「 <A href="lync-server-2013-planning-for-autodiscover.md">Lync Server 2013 での自動検出の計画</A>」をご覧ください。

    
    </div>

  - **プッシュ通知サービス**   このサービスは、Lync Online データセンターにあるクラウドベースのサービスです。 サポートされている Apple iOS デバイスまたは Windows Phone の Lync モバイルアプリケーションが非アクティブになっていると、新しいインスタントメッセージ (IM) の招待、不在着信メッセージ、不在着信、ボイスメールなど、これらのデバイスはサポートされていないため、新しいイベントに応答できません。バックグラウンドで実行されているモバイルアプリケーション。 このような場合には、新しいイベントの通知 (*プッシュ通知*と呼ばれる) がモバイルデバイスに送信されます。 モバイルサービスはクラウドベースのプッシュ通知サービスに通知を送信します。これにより、Apple Push Notification Service (APNS) (サポートされている Apple iOS デバイスの場合) または Microsoft プッシュ通知サービス (MPNS) に通知が送信されます。) (Windows Phone の場合) がモバイルデバイスに送信されます。 ユーザーは、モバイルデバイスで通知に応答して、アプリケーションをアクティブ化することができます。
    
    Apple と Windows Phone デバイス上の Lync 2010 Mobile では、プッシュ通知が使われます。 Apple デバイス向け Lync 2013 モバイルクライアントは、Lync Server 2013 の累積更新プログラムで導入されました。年2月 7 2013 日に、プッシュ通知またはプッシュ通知のクリアリングハウス (PNCH) を使用しなくなりました。

次の図は、UCWA と Lync 2013 モバイルクライアントを使用する Lync Server 2013 トポロジ内でプッシュ通知サービスがどのように適合するかを示しています。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

Lync Server 2010 向けの累積的な更新プログラムで導入されました: 2011 年11月、Mcx サービスは Lync 2010 モバイルクライアントにサービスを提供します。 次の図は、Mcx と Lync 2010 モバイルクライアントを使用したトポロジに適用される、プッシュ通知サービスを示しています。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>サポートされるトポロジ

Lync Server 2013 の累積的な更新プログラムの適用: 2013 年2月に、次のトポロジでの Lync 2013 モバイルクライアント機能の機動性をサポートするために、UCWA web コンポーネントが追加されます。

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

エッジサーバーは、Lync Server 2010 Edge サーバーにすることができます。

Lync server 2013 の累積更新プログラムが適用されていない Lync Server 2013 の展開: 2013 年2月は、Mcx Mobility Service を使用し、Lync 2010 Mobile のサービスのみを提供します。

<div>


> [!IMPORTANT]  
> モバイルサービスは、2つのネットワークインターフェイスで仲介サーバーの役割と連携しているフロントエンドサーバーでサポートされますが、インターフェイスを構成するための適切な手順を実行する必要があります。 仲介サーバーとして通信する特定のインターフェイスと、フロントエンドサーバーとして通信するネットワークインターフェイス IP に IP アドレスを割り当てる必要があります。 これを行うには、トポロジビルダーで、既定の [<STRONG>すべての構成された ip アドレスを使用</STRONG>する] ではなく、各サービスの正しい ip アドレスを選択します。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)  
[Lync Server 2013 での自動検出の計画](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


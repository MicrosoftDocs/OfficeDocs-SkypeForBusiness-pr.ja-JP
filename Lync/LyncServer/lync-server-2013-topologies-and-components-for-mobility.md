---
title: 'Lync Server 2013: モビリティのトポロジとコンポーネント'
TOCTitle: モビリティのトポロジとコンポーネント
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48273457
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のモビリティのトポロジとコンポーネント

 

_**トピックの最終更新日:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

モバイル デバイスで Lync モバイル アプリケーションをサポートするために、Lync Server 2013 では、Lync Server 2013 の Mcx Mobility Service、Lync Server 2013 の自動検出サービス、および Lync Server 2013 のプッシュ通知サービスの 3 つのサービスを提供します。Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月では、Lync 2013 モバイル クライアント向けの高度なサービス (統合コミュニケーション Web API (UCWA) によるモビリティのサポート) が無料で追加されています。このセクションでは、これらのコンポーネントについて簡単に説明し、モビリティをサポートする Lync Server 2013 トポロジを確認します。

> [!NOTE]
> モビリティ サービスは、ハイブリッド展開でも利用できます。ユーザーが常時オンラインである場合はモビリティをサポートするためのサービスを展開する必要はありません。モバイル ユーザーが自分のオンライン ID を検索できるようにするために、自動検出サービスの設定を定義する必要があります。



> [!IMPORTANT]
> 何らかの外部ユーザーによる接続 (たとえば、フェデレーション、外部ユーザー アクセス、またはモビリティ機能) を計画している場合、 Standard Edition サーバーを使用した エッジ サーバー と、 フロント エンド サーバーまたは フロント エンド プールを使用する必要があります。 Standard Edition サーバーと、 フロント エンド サーバーまたは フロント エンド プールには、外部ユーザーが内部展開にアクセスできるようにするか、または内部展開が外部ユーザーと通信できるようにするための必須のコンポーネントはありません。モビリティを含め、外部ユーザーが内部ユーザーと共同作業または通信を行うあらゆるシナリオで、少なくとも 1 つの エッジ サーバーと 1 つのリバース プロキシが必要になります。<BR><EM>プッシュ通知</EM>では、Push Notification Clearing House (PNCH) をホストする Lync Online サービスに対する一種のフェデレーションを使用します。プッシュ通知とは、警告音、画面上の警告 (テキスト) のほか、モバイル デバイスが非アクティブのときに、アプリケーションによって Apple iPhone、iPad、Windows Phone にプッシュ配信されるバッジを指します。PNCH は、Lync Server からプッシュ通知を受け取ります。PNCH は、メッセージを通知として受け取ると、メッセージの送信先として意図されたモバイル クライアントに基づいて、Apple Push Notification Service または Lync Server 2013 Push Notification Service を通じてモバイル クライアントに通知を転送します。PNCH は、これらのモバイル クライアントにとって必須のサービスです。PNCH は、Lync Online に対するフェデレーションを行うために、エッジ サーバー、機密性と認証を確保するための証明書、ポリシー、および正しく構成されたドメイン ネーム システム (DNS) レコードを使用します。Nokia Symbian および Android ベースの Lync Mobile クライアントは、PNCH を使用しません。エッジ サーバーのプランニングと展開の詳細については、「<A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013 の外部ユーザー アクセスの計画</A>」および「<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 での外部ユーザー アクセスの展開</A>」を参照してください。<BR>Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月で導入された Apple デバイス向けの Lync 2013 モバイル クライアントは、プッシュ通知または Push Notification Clearing House (PNCH) を使用しません。 Windows Phone の Lync 2013 モバイル クライアントは、引き続きプッシュ通知および PNCH を使用します。



## モビリティ コンポーネント

モビリティをサポートするサービスは次のとおりです。

  - **Lync Server 2013 統合コミュニケーション Web API (UCWA)**    Lync Server 2013 でのモバイルおよび Web クライアントとのリアルタイム通信用のサービスを提供します。Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月を フロント エンド サーバーと ディレクターに展開すると、インストールにより、内部および外部 Web サービスに仮想ディレクトリ (Ucwa) が作成されます。Ucwa 仮想ディレクトリに属する Web コンポーネントは、UCWA 対応のクライアントからの通話を受け付けます。クライアント アプリケーションは、プレゼンス、連絡先、インスタント メッセージング、VoIP、ビデオ会議、コラボレーション用の REST インターフェイスを介して通信します。UCWA では、P-GET ベースのチャネルを使用して、着信通話、着信インスタント メッセージ、メッセージなどのイベントをクライアント アプリケーションに送信します。
    
    > [!NOTE]
    > <em>REST</em> (Representational State Transfer) は、多くのファームで広範囲に採用されている、配信システム向けのソフトウェア アーキテクチャ スタイルで、一般的に Web サービスの要件に適しています。


  - **Lync Server 2013 Mobility Service (Mcx)**   このサービスは、インスタント メッセージング (IM)、プレゼンス、連絡先などの Lync 機能を、モバイル デバイスでサポートします。Mobility Service は、各プールのすべての フロント エンド サーバーにインストールされ、モバイル デバイス上で Lync 機能をサポートします。 Lync Server 2013 をインストールすると、新しい仮想ディレクトリ (Mcx) が フロント エンド サーバーの内部 Web サイトおよび外部 Web サイトの両方に作成されます。
    

    > [!IMPORTANT]
    > Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月が適用された Lync Server 2013 では、Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月で導入された Mobility Service (一般に Mcx と呼ばれる) と UCWA Web コンポーネントの両方をサポートします。この 2 つの Mobility Service を組み合わせると、 Lync Server 2013 上の Lync 2010 Mobile および Lync 2013 モバイル クライアントとの相互運用とユーザーの利用が可能になります。



  - **Lync Server 2013 自動検出サービス**   このサービスはユーザーの場所を特定します。さらに、Lync Server 2013 Web サービス用の内部および外部 URL、Mcx または UCWA 用の URL などのリソースを、ネットワークの場所にかかわらず、モバイル デバイスやその他の Lync クライアントが検出できるようにします。自動検出は、ハードコードされたホスト名 (ネットワーク内部のユーザーの場合は lyncdiscoverinternal、ネットワーク外部のユーザーの場合は lyncdiscover) およびユーザーの SIP ドメインを使用します。また、HTTP または HTTPS のどちらかを使用するクライアント接続をサポートします。
    
    自動検出サービスは、すべての フロント エンド サーバーと各プールのすべての ディレクターにインストールされ、モバイル デバイスで Lync 機能をサポートします。自動検出サービスをインストールすると、新しい仮想ディレクトリ (Autodiscover) が フロント エンド サーバーと ディレクターの内部および外部 Web サイトに作成されます。
    
    > [!NOTE]
    > 自動検出サービスは、モバイル クライアント サービスの提供時に引き続き重要なコンポーネントなので、ここに記載されています。すべてのクライアントに対してサービスを提供するために、 Lync Server 2013 における自動検出の役割が拡張されました。自動検出サービスの計画に関する詳細については、「<a href="lync-server-2013-planning-for-autodiscover.md">自動検出の計画</a>」を参照してください。


  - **プッシュ通知サービス**   このサービスは、クラウドベースのサービスで、Lync Online データセンターに存在します。サポートされている Apple iOS デバイスまたは Windows Phone の Lync モバイル アプリケーションは、非アクティブの場合、新しいインスタント メッセージング (IM) の招待状、不在着信のインスタント メッセージ、不在着信、ボイス メールなどの新しいイベントに応答できません。これは、これらのデバイスがバックグラウンドで動作するモバイル アプリケーションをサポートしないためです。このような場合、新しいイベント用の*プッシュ通知*と呼ばれる通知がモバイル デバイスに送信されます。Mobility Service は、通知をクラウドベースのプッシュ通知サービスに送信し、プッシュ通知サービスはその通知を Apple Push Notification Service (APNS) (サポートされている Apple iOS デバイス用) または Microsoft Push Notification Service (MPNS) (Windows Phone 用) に送信します。最後に、APNS または MPNS がその通知をモバイル デバイスに送信します。その後、ユーザーはモバイル デバイス上でこの通知にアクセスしてアプリケーションをアクティブにすることができます。
    
    Apple デバイスまたは Windows Phone デバイス上の Lync 2010 Mobile では、プッシュ通知を使用します。Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月で導入された Apple デバイス用の Lync 2013 モバイル クライアントは、プッシュ通知または Push Notification Clearing House (PNCH) を使用しません。

次の図は、プッシュ通知サービスが UCWA および Lync 2013 モバイル クライアントを使用する Lync Server 2013 トポロジとどのように適合しているかを示しています。

![プッシュ通知サービス UCWA](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "プッシュ通知サービス UCWA")

Mcx サービスは、 Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月で導入され、 Lync 2010 Mobile クライアント向けのサービスを提供します。次の図は、Mcx および Lync 2010 Mobile クライアントを使用するトポロジに適用されるプッシュ通知サービスを示しています。

![プッシュ通知サービス MCX](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "プッシュ通知サービス MCX")

## サポートされるトポロジ

Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月を適用すると、次のトポロジで Lync 2013 モバイル クライアント機能用のモビリティをサポートするために、UCWA Web コンポーネントが追加されます。

  - Lync Server 2013  Standard Edition

  - Lync Server 2013 Enterprise Edition

エッジ サーバーは Lync Server 2010  エッジ サーバーになります。

Lync Server 2013 の累積的な更新プログラム: 2013 年 2 月が適用されていない Lync Server 2013 の展開では、Mcx Mobility Service を使用し、 Lync 2010 Mobile に対してのみサービスを提供できます。


> [!IMPORTANT]
> Mobility Service は、 仲介サーバーの役割と併置される フロント エンド サーバーで、2 つのネットワーク インターフェイスを使用してサポートされますが、適切な手順を使用してインターフェイスを構成する必要があります。 仲介サーバーとして通信する特定のインターフェイスと、 フロント エンド サーバーとして通信するネットワーク インターフェイス IP に対して IP アドレスを割り当てる必要があります。 トポロジ ビルダーで割り当てを行うには、既定の [<STRONG>すべての構成済み IP アドレスを使用する</STRONG>] を使用するのではなく、サービスごとに適切な IP アドレスを選択します。



## 関連項目

#### その他のリソース

[Lync Server 2013 の外部ユーザー アクセスの計画](lync-server-2013-planning-for-external-user-access.md)  
[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)  
[自動検出の計画](lync-server-2013-planning-for-autodiscover.md)


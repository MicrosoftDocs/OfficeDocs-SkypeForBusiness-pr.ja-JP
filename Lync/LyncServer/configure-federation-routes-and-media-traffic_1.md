---
title: フェデレーション ルートとメディア トラフィックの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840784"
---
# <a name="configure-federation-routes-and-media-traffic"></a>フェデレーション ルートとメディア トラフィックの構成

 


フェデレーションは、2つ以上の SIP ドメイン間の信頼関係であり、別々の組織のユーザーがネットワーク境界を越えて通信することを許可します。 Lync Server 2013 パイロットプールに移行した後、Microsoft Office Communications Server 2007 R2 Edge サーバーのフェデレーションルートから、Lync Server 2013 Edge サーバーのフェデレーションルートに移行する必要があります。

次の手順に従って、フェデレーションルートとメディアトラフィックルートを Office Communications Server 2007 R2 Edge サーバーとディレクターから Lync Server 2013 Edge サーバーに移行して、単一サイト展開を行います。


> [!IMPORTANT]  
> フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Office Communications Server 2007 R2 Edge サーバーのメンテナンスダウンタイムをスケジュールする必要があります。 この切り替えプロセス全体は、停止期間中はフェデレーションアクセスを使用できないことを意味します。 最小限のユーザーアクティビティが想定されている場合は、ダウンタイムのスケジュールを設定する必要があります。 また、エンドユーザーに十分な通知も提供する必要があります。 この停止に応じて計画し、組織内で適切な期待を設定します。




> [!IMPORTANT]  
> 従来の Office Communications Server 2007 R2 Edge サーバーが、アクセスエッジサービス、Web 会議エッジサービス、および A/V Edge サービスに同じ FQDN を使用するように構成されている場合は、このセクションの手順でフェデレーション設定を Lync サーバーに移行します。2013エッジサーバーはサポートされていません。 従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まず、すべてのユーザーを Office Communications Server 2007 R2 から Lync Server 2013 に移行してから、フェデレーションを有効にする前に Office Communications Server 2007 R2 Edge サーバーを非コミッションにする必要があります。Lync Server 2013 エッジサーバー。 詳細については、次のトピックを参照してください。 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013 への残りのユーザーの移動</A></P>
> <LI>
> <P>"サーバーとサーバーの役割を削除する"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> お使いの XMPP フェデレーションが Lync Server 2013 Edge サーバー経由でルーティングされている場合、従来の Office Communications Server 2007 R2 ユーザーは、すべてのユーザーが Lync Server 2013、XMPP ポリシー、および証明書が構成されていて、[XMPP フェデレーションパートナー] が Lync Server 2013 で構成されていて、最後に DNS エントリが更新されています。



トポロジを正常に発行、有効化、または無効にするには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。 また、サーバーの役割を追加するための適切なユーザー権限と権限を委任することもできます。 詳細については、Standard Edition server または Enterprise Edition server 展開ドキュメントの「 [Lync server 2013 でのセットアップ権限の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。 その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 サイトから従来のフェデレーション関連付けを削除するには

1.  トポロジビルダーを使用して、パイロットプールトポロジを開きます。

2.  左側のウィンドウで、サイトノードに移動します。

3.  サイトを右クリックし、[プロパティの**編集**] をクリックします。

4.  左側のウィンドウで [**フェデレーションルート**] を選びます。

5.  [サイトフェデレーションルートの割り当て] で、[ **SIP フェデレーションを有効**にする] の横にあるチェックボックスをオフにして、 **BackCompatSite**経由でフェデレーションルートを無効にします。
    
    ![[プロパティの編集] ダイアログ、フェデレーションルート](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[プロパティの編集] ダイアログ、フェデレーションルート")

6.  [ **OK]** をクリックして、[プロパティの編集] ページを閉じます。

7.  [**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。

8.  [**アクション**] メニューで、[**トポロジの発行**] をクリックしてウィザードを完了します。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>レガシエッジサーバーを非フェデレーションエッジサーバーとして構成するには

1.  **トポロジビルダー**から、[**アクション**] メニューの [ **Office Communications Server 2007 R2 トポロジの結合**] をクリックします。

2.  [**次へ**] をクリックして続行します。

3.  [ **Edge セットアップの指定**] で、フェデレーション用に現在構成されている**エッジサーバーの内部 FQDN**を選択し、[**変更**] をクリックします。
    
    ![OCS 2007 R2 トポロジの結合、エッジ設定の指定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 トポロジの結合、エッジ設定の指定")

4.  [**次へ**] をクリックし、[**外部エッジの指定**] ページに移動するまで既定の設定をそのまま使用します。
    
    ![トポロジビルダーの外部エッジページを指定する](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "トポロジビルダーの外部エッジページを指定する")

5.  [**外部エッジの指定**] で、[**このエッジプールをフェデレーションおよびパブリック IM 接続に使用する**] チェックボックスをオフにします。 これにより、BackCompatSite とのフェデレーション関連付けが削除されます。
    

    > [!IMPORTANT]  
    > この手順は重要です。 従来のフェデレーションの関連付けを削除するには、このオプションをオフにする必要があります。



6.  [**次へ**] をクリックして、ウィザードの残りのページの既定の設定をそのまま使用します。

7.  [**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。

8.  [**状態**] 列で、値が**成功**していることを確認し、[**完了**] をクリックしてウィザードを閉じます。

9.  [**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。

10. **発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。
    
    ![マージ後にサイトが表示されたトポロジビルダー](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "マージ後にサイトが表示されたトポロジビルダー")
    
    前の図に示すように、[**サイトフェデレーションルートの割り当て**] の下にある**SIP フェデレーション**は**無効**に設定されています。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Lync Server 2013 エッジサーバーで証明書を構成するには

1.  従来の Office Communications Server 2007 R2 Edge サーバーから、秘密キーを持つ外部アクセスプロキシ証明書をエクスポートします。

2.  Lync Server 2013 エッジサーバー上で、前の手順でアクセスプロキシの外部証明書をインポートします。

3.  アクセスプロキシの外部証明書を、エッジサーバーの Lync Server 2013 外部インターフェイスに割り当てます。

4.  Lync Server 2013 Edge サーバーの内部インターフェイス証明書を変更しないでください。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Lync Server 2013 エッジサーバーを使用するように Office Communications Server 2007 R2 フェデレーションルートを変更するには

1.  Office Communications Server 2007 R2 Standard Edition サーバーまたはフロントエンドサーバーで、Office Communications Server 2007 R2 管理ツールを開きます。

2.  左側のウィンドウで、最上位のノードを展開し、[**フォレスト**] ノードを右クリックします。 [**プロパティ**] を選択し、[**グローバルプロパティ**] をクリックします。

3.  [**フェデレーション**] タブをクリックします。

4.  フェデレーションおよびパブリック IM 接続を有効にするには、このチェックボックスをオンにします。

5.  Lync Server 2013 エッジサーバーの FQDN を入力し、[ **OK]** をクリックします。
    
    ![OCS グローバルプロパティの [フェデレーション] タブ](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS グローバルプロパティの [フェデレーション] タブ")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 Edge Server フェデレーションを有効にするには

1.  [トポロジビルダー] の左側のウィンドウで、[Lync Server 2013 **Edge プール**] ノードに移動します。

2.  ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。
    

    > [!NOTE]  
    > フェデレーションは、1つのエッジプールに対してのみ有効にすることができます。 エッジプールが複数ある場合は、フェデレーションエッジプールとして使用するためにいずれかを選択します。



3.  [**全般**] ページで、[**このエッジプールのフェデレーションを有効にする (Port 5061)** ] チェックボックスをオンにします。
    
    ![プロパティを編集する、一般に、エッジフェデレーションを有効にする](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "プロパティを編集する、一般に、エッジフェデレーションを有効にする")

4.  [ **OK]** をクリックして、[プロパティの編集] ページを閉じます。

5.  次に、サイトノードに移動します。

6.  サイトを右クリックし、[プロパティの**編集**] をクリックします。

7.  左側のウィンドウで、[**フェデレーションルート**] をクリックします。

8.  [**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、一覧から [Lync server 2013 Edge server] を選びます。

9.  [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。
    
    ![[プロパティの編集]、[全般]、[Edge プールの関連付け]](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "[プロパティの編集]、[全般]、[Edge プールの関連付け")]
    
    複数サイト展開の場合は、各サイトでこの手順を実行します。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 Edge Server の送信メディアパスを構成するには

1.  [**トポロジビルダー**] から、 **Standard Edition のフロントエンドサーバー**または**Enterprise Edition のフロントエンドプール**の下にある Lync Server 2013 プールに移動します。

2.  プールを右クリックし、[プロパティの**編集**] をクリックします。

3.  [**関連付け**] セクションで、[ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにします。

4.  ドロップダウンボックスで、Lync Server 2013 エッジサーバーを選びます。
    
    ![[プロパティの編集] ダイアログ、[Edge プールの関連付け]](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[プロパティの編集] ダイアログ、[Edge プールの関連付け]")

5.  [ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。

## <a name="to-publish-edge-server-configuration-changes"></a>エッジサーバー構成の変更を公開するには

1.  [**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。

2.  [**アクション**] メニューで、[**トポロジの公開**] を選択し、ウィザードを完了します。

3.  展開内のすべてのプールに対して Active Directory のレプリケーションが行われるのを待ちます。
    

    > [!NOTE]  
    > 次のメッセージが表示されることがあります。<BR><STRONG>警告: トポロジに複数のフェデレーションエッジサーバーが含まれています。これは、製品の最新バージョンへの移行中に発生する可能性があります。その場合は、1つのエッジサーバーのみがフェデレーションに対してアクティブに使用されます。外部 DNS SRV レコードが適切なエッジサーバーを指していることを確認します。複数のフェデレーションエッジサーバーを展開して同時にアクティブにするには (つまり、移行シナリオではなく)、すべてのフェデレーションパートナーが Office Communications Server 2007 R2 または Lync Server を使用していることを確認します。外部 DNS SRV レコードに、すべてのフェデレーションが有効なエッジサーバーの一覧が表示されていることを確認します。</STRONG><BR>この警告は予期されるものであり、無視しても問題ありません。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモートアクセスを確認するには

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  フェデレーションとリモートアクセスの状態を確認するには、コマンドラインで次のように入力します。
    
        Get-CsAccessEdgeConfiguration

3.  フェデレーションおよびリモートアクセスを有効にするには、コマンドラインで次のように入力します。
    
        Set-CsAccessEdgeConfiguration
    
    これらのコマンドレットの詳細については、次のトピックを参照してください。 [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\))と[CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\))を参照してください。

4.  Lync Server 2013 エッジサーバーをオンラインにしてから、フェデレーションと外部アクセスをテストする前に、レプリケーションが完了するまで待ちます。

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 エッジサーバーを構成するには

1.  すべての Lync Server 2013 エッジサーバーをオンラインにします。

2.  外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを、従来のエッジサーバーではなく、Lync Server 2013 エッジサーバーに送信するには、外部ファイアウォールルーティングルールまたはハードウェアロードバランサーの設定を更新します。
    

    > [!NOTE]  
    > ハードウェアロードバランサーを持っていない場合は、新しい Lync Server アクセスエッジサーバーを解決するために、フェデレーション用の DNS A レコードを更新する必要があります。 これを最小限の中断で実現するには、外部の Lync Server アクセスエッジ FQDN の TTL 値を減らして、新しい Lync Server アクセスエッジサーバーをポイントするように DNS が更新されると、フェデレーションとリモートアクセスがすぐに更新されるようにします。



3.  次に、各エッジサーバーコンピューターから**Lync Server アクセスエッジ**を停止します。

4.  各レガシエッジサーバーコンピューターで、[**管理ツール**] の [**サービス**] アプレットを開きます。

5.  [サービス] ボックスの一覧で、[ **Office Communications Server アクセスエッジ**] を見つけます。

6.  [サービス名] を右クリックし、[**停止**] を選択してサービスを停止します。

7.  [スタートアップの種類を**無効**に設定します。

8.  [ **OK** ] をクリックして、[**プロパティ**] ウィンドウを閉じます。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>外部ユーザーと外部アクセスの接続性をテストするには

  - 少なくとも1つのフェデレーションドメインのユーザー。 Lync Server 2013 上の内部ユーザーと、Office Communications Server 2007 R2 上のユーザー。 インスタントメッセージング (IM)、プレゼンス、音声/ビデオ (A/V)、デスクトップ共有をテストします。

  - 組織がサポートしている各パブリック IM サービスプロバイダーのユーザー (およびプロビジョニングが完了した場合) は、Lync Server 2013 および Office Communications Server 2007 R2 上のユーザーと通信します。

  - 匿名ユーザーが会議に参加できることを確認します。

  - Office Communications Server 2007 R2 でホストされているユーザー 2007 (リモートユーザーアクセス) を使って、Lync Server 2013、および Office Communications Server 2007 R2 上のユーザーとの間で、VPN を使用せずに office communications server R2 でホストされているユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

  - Lync server 2013 でホストされているユーザー (イントラネットの外部から Lync server 2013 にログインしていますが、VPN を使用しません)。 Lync Server 2013、および Office Communications Server 2007 R2 上のユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

